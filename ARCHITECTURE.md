# Architecture Documentation

This document provides an overview of the system architecture for the Full Stack Realtime Chat Application.

## Table of Contents

- [System Overview](#system-overview)
- [Technology Stack](#technology-stack)
- [Architecture Diagram](#architecture-diagram)
- [Backend Architecture](#backend-architecture)
- [Frontend Architecture](#frontend-architecture)
- [Database Schema](#database-schema)
- [API Design](#api-design)
- [Real-time Communication](#real-time-communication)
- [Authentication Flow](#authentication-flow)
- [Deployment Architecture](#deployment-architecture)

---

## System Overview

The application follows a **client-server architecture** with real-time bidirectional communication using WebSockets. It's built using the MERN stack (MongoDB, Express, React, Node.js) with Socket.io for real-time features.

### Key Components

1. **Frontend (React)** - Single Page Application (SPA)
2. **Backend (Node.js/Express)** - RESTful API + WebSocket server
3. **Database (MongoDB)** - NoSQL document database
4. **File Storage (Cloudinary)** - Cloud-based image storage
5. **Real-time Engine (Socket.io)** - WebSocket communication

---

## Technology Stack

### Frontend
```
React 18.x
├── Vite (Build tool)
├── React Router (Routing)
├── Zustand (State management)
├── Axios (HTTP client)
├── Socket.io Client (WebSocket)
├── TailwindCSS (Styling)
└── DaisyUI (UI components)
```

### Backend
```
Node.js 18.x
├── Express (Web framework)
├── MongoDB + Mongoose (Database)
├── Socket.io (WebSocket server)
├── JWT (Authentication)
├── Bcrypt (Password hashing)
├── Cloudinary (Image storage)
└── Cookie Parser (Cookie handling)
```

---

## Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                         CLIENT LAYER                         │
├─────────────────────────────────────────────────────────────┤
│  React Components  │  Zustand Stores  │  Socket.io Client   │
│  ─────────────────────────────────────────────────────────  │
│  Pages │ Components │ Auth │ Chat │ Theme │ WebSocket       │
└────────────────────┬────────────────────────┬───────────────┘
                     │                        │
                     │ HTTP/HTTPS             │ WebSocket
                     │ (REST API)             │ (Real-time)
                     │                        │
┌────────────────────┴────────────────────────┴───────────────┐
│                      APPLICATION LAYER                       │
├─────────────────────────────────────────────────────────────┤
│              Express.js + Socket.io Server                   │
│  ─────────────────────────────────────────────────────────  │
│  Routes │ Controllers │ Middleware │ Socket Handlers        │
└────────────────────┬────────────────────────┬───────────────┘
                     │                        │
                     │                        │
┌────────────────────┴────────────────────────┴───────────────┐
│                       DATA LAYER                             │
├─────────────────────────────────────────────────────────────┤
│  MongoDB (Mongoose)  │  Cloudinary API  │  JWT Tokens       │
│  ─────────────────────────────────────────────────────────  │
│  Users │ Messages    │  Images          │  Authentication   │
└─────────────────────────────────────────────────────────────┘
```

---

## Backend Architecture

### Directory Structure

```
backend/src/
├── controllers/          # Request handlers
│   ├── auth.controller.js
│   └── message.controller.js
├── models/              # Database models
│   ├── user.model.js
│   └── message.model.js
├── routes/              # API routes
│   ├── auth.routes.js
│   └── message.routes.js
├── middleware/          # Custom middleware
│   └── auth.middleware.js
├── lib/                 # Utilities
│   ├── db.js           # Database connection
│   ├── socket.js       # Socket.io setup
│   ├── cloudinary.js   # Cloudinary config
│   └── utils.js        # Helper functions
├── seeds/              # Database seeders
│   └── user.seed.js
└── index.js            # Entry point
```

### Layers

1. **Routes Layer** - Defines API endpoints
2. **Controller Layer** - Business logic
3. **Model Layer** - Data models and database interaction
4. **Middleware Layer** - Authentication, validation, error handling
5. **Service Layer** - External services (Cloudinary, Socket.io)

### Design Patterns

- **MVC Pattern** - Model-View-Controller separation
- **Middleware Pattern** - Request/response processing pipeline
- **Repository Pattern** - Data access abstraction (Mongoose models)
- **Singleton Pattern** - Database connection, Socket.io instance

---

## Frontend Architecture

### Directory Structure

```
frontend/src/
├── components/          # Reusable components
│   ├── Navbar.jsx
│   ├── Sidebar.jsx
│   ├── ChatContainer.jsx
│   ├── MessageInput.jsx
│   └── skeletons/      # Loading skeletons
├── pages/              # Page components
│   ├── HomePage.jsx
│   ├── LoginPage.jsx
│   ├── SignUpPage.jsx
│   ├── ProfilePage.jsx
│   └── SettingsPage.jsx
├── store/              # Zustand stores
│   ├── useAuthStore.js
│   ├── useChatStore.js
│   └── useThemeStore.js
├── lib/                # Utilities
│   ├── axios.js        # Axios instance
│   └── utils.js        # Helper functions
├── constants/          # Constants
│   └── index.js
├── App.jsx             # Root component
└── main.jsx            # Entry point
```

### State Management

**Zustand Stores:**

1. **authStore** - User authentication state
   - User data
   - Login/logout functions
   - Auth check

2. **chatStore** - Chat functionality
   - Messages
   - Selected user
   - Online users
   - Send/receive message functions

3. **themeStore** - UI theme
   - Current theme
   - Theme switching

### Component Hierarchy

```
App
├── Navbar
├── Routes
│   ├── HomePage
│   │   ├── Sidebar
│   │   │   └── UserList
│   │   └── ChatContainer
│   │       ├── ChatHeader
│   │       ├── MessageList
│   │       └── MessageInput
│   ├── LoginPage
│   ├── SignUpPage
│   ├── ProfilePage
│   └── SettingsPage
```

---

## Database Schema

### User Model

```javascript
{
  _id: ObjectId,
  email: String (unique, required),
  fullName: String (required),
  password: String (hashed, required),
  profilePic: String (URL),
  createdAt: Date,
  updatedAt: Date
}
```

### Message Model

```javascript
{
  _id: ObjectId,
  senderId: ObjectId (ref: User, required),
  receiverId: ObjectId (ref: User, required),
  text: String,
  image: String (URL),
  createdAt: Date,
  updatedAt: Date
}
```

### Indexes

- `User.email` - Unique index for fast lookup
- `Message.senderId` - Index for sender queries
- `Message.receiverId` - Index for receiver queries
- `Message.createdAt` - Index for sorting

---

## API Design

### RESTful Endpoints

#### Authentication
```
POST   /api/auth/signup      - Register new user
POST   /api/auth/login       - Login user
POST   /api/auth/logout      - Logout user
GET    /api/auth/check       - Check auth status
PUT    /api/auth/update-profile - Update profile
```

#### Messages
```
GET    /api/messages/users   - Get all users
GET    /api/messages/:id     - Get messages with user
POST   /api/messages/send/:id - Send message to user
```

### Request/Response Format

**Request:**
```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "_id": "123",
    "email": "user@example.com",
    "fullName": "John Doe"
  },
  "message": "Login successful"
}
```

---

## Real-time Communication

### Socket.io Events

#### Client → Server
```javascript
"connect"           // Client connects
"disconnect"        // Client disconnects
```

#### Server → Client
```javascript
"getOnlineUsers"    // Send list of online users
"newMessage"        // Broadcast new message
```

### Connection Flow

1. User authenticates via HTTP
2. Client establishes WebSocket connection
3. Server stores user's socket ID
4. Server broadcasts online users
5. Messages sent via Socket.io
6. On disconnect, server updates online users

---

## Authentication Flow

```
1. User Registration
   ├── Client sends credentials
   ├── Server validates input
   ├── Server hashes password (bcrypt)
   ├── Server creates user in DB
   ├── Server generates JWT token
   └── Server sends token in cookie

2. User Login
   ├── Client sends credentials
   ├── Server validates credentials
   ├── Server compares password hash
   ├── Server generates JWT token
   └── Server sends token in cookie

3. Protected Routes
   ├── Client sends request with cookie
   ├── Middleware verifies JWT token
   ├── Middleware attaches user to request
   └── Controller processes request

4. User Logout
   ├── Client sends logout request
   ├── Server clears JWT cookie
   └── Client clears local state
```

---

## Deployment Architecture

### Production Setup

```
┌─────────────────┐
│   CloudFlare    │  (CDN + DDoS Protection)
└────────┬────────┘
         │
┌────────┴────────┐
│  Load Balancer  │  (Optional)
└────────┬────────┘
         │
    ┌────┴────┐
    │         │
┌───┴───┐ ┌──┴────┐
│ App 1 │ │ App 2 │  (Node.js instances)
└───┬───┘ └──┬────┘
    │        │
    └────┬───┘
         │
┌────────┴────────┐
│   MongoDB Atlas │  (Database)
└─────────────────┘
         │
┌────────┴────────┐
│   Cloudinary    │  (Image storage)
└─────────────────┘
```

### Environment Configuration

- **Development**: Local MongoDB, local file storage
- **Staging**: MongoDB Atlas, Cloudinary
- **Production**: MongoDB Atlas, Cloudinary, CDN

---

## Security Considerations

1. **Authentication**: JWT tokens with httpOnly cookies
2. **Password**: Bcrypt hashing (10 rounds)
3. **Input Validation**: Server-side validation
4. **CORS**: Configured for specific origins
5. **Rate Limiting**: Prevent abuse (to be implemented)
6. **SQL Injection**: Mongoose parameterized queries
7. **XSS**: React auto-escaping, Content Security Policy

---

## Performance Optimizations

1. **Database**: Indexed queries, connection pooling
2. **Frontend**: Code splitting, lazy loading, memoization
3. **Images**: Cloudinary optimization, lazy loading
4. **Caching**: Browser caching, service workers (planned)
5. **Bundle Size**: Tree shaking, minification

---

## Scalability Considerations

1. **Horizontal Scaling**: Multiple Node.js instances
2. **Load Balancing**: Distribute traffic
3. **Database Sharding**: For large datasets
4. **Redis**: For session storage and Socket.io adapter
5. **Microservices**: Split into smaller services (future)

---

**Last Updated:** January 2024
