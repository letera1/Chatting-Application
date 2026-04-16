# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2024-01-01

### Added
- Real-time messaging with Socket.io
- User authentication and authorization with JWT
- Online user status tracking
- Profile management with avatar upload
- Image sharing in messages via Cloudinary
- Theme customization (multiple color themes)
- Responsive design with TailwindCSS and DaisyUI
- Global state management with Zustand
- MongoDB database integration
- User seed data for testing

### Features
- **Authentication**
  - User registration with email validation
  - Secure login with JWT tokens
  - Password hashing with bcrypt
  - Protected routes and middleware

- **Messaging**
  - Real-time message delivery
  - Message history persistence
  - Image attachments support
  - Typing indicators
  - Message timestamps

- **User Interface**
  - Clean and modern design
  - Multiple theme options
  - Responsive layout for all devices
  - Sidebar with user list
  - Chat container with message history
  - Profile page with avatar upload

- **Real-time Features**
  - Online/offline user status
  - Instant message delivery
  - Socket.io integration
  - Connection state management

### Technical Stack
- **Frontend**: React, Vite, TailwindCSS, DaisyUI, Zustand, Socket.io-client
- **Backend**: Node.js, Express, MongoDB, Socket.io, JWT, Cloudinary
- **Deployment**: Production-ready configuration

### Security
- JWT-based authentication
- Password hashing
- Protected API routes
- Environment variable configuration
- Input validation and sanitization

---

## [Unreleased]

### Planned Features
- Group chat functionality
- Voice messages
- Video calls
- Message reactions
- Message search
- User blocking
- Push notifications
- Message encryption
- File sharing (documents, videos)
- Message editing and deletion
- Read receipts

---

## How to Update

To update to the latest version:

```bash
git pull origin main
npm run build
npm start
```

Make sure to update your `.env` file if new environment variables are added.
