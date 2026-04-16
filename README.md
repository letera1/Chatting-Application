# ✨ Full Stack Realtime Chat Application

<div align="center">

![Demo App](/frontend/public/screenshot-for-readme.png)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js Version](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)](https://nodejs.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

[Video Tutorial](https://youtu.be/ntKkVrQqBYY) • [Report Bug](https://github.com/yourusername/chat-app/issues) • [Request Feature](https://github.com/yourusername/chat-app/issues)

</div>

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 About

A modern, full-stack real-time chat application built with the MERN stack. This application provides seamless real-time communication with a beautiful, responsive UI and robust backend architecture.

### Key Highlights

- 🌟 **Modern Tech Stack**: MERN + Socket.io + TailwindCSS + DaisyUI
- 🔐 **Secure Authentication**: JWT-based authentication and authorization
- 💬 **Real-time Messaging**: Instant message delivery with Socket.io
- 🟢 **Online Status**: Live user presence indicators
- 🎨 **Theme Customization**: Multiple color themes to choose from
- 📱 **Responsive Design**: Works seamlessly on all devices
- 🖼️ **Image Sharing**: Upload and share images via Cloudinary
- ⚡ **State Management**: Efficient global state with Zustand
- 🐞 **Error Handling**: Comprehensive error handling on client and server
- 🚀 **Production Ready**: Optimized for deployment

---

## ✨ Features

### Authentication & Authorization
- User registration with validation
- Secure login with JWT tokens
- Password hashing with bcrypt
- Protected routes and middleware
- Persistent authentication

### Real-time Messaging
- Instant message delivery
- Message history persistence
- Image attachments support
- Online/offline user status
- Socket.io integration
- Message timestamps

### User Interface
- Clean and modern design
- Multiple theme options (29+ themes)
- Responsive layout for all devices
- Sidebar with user list
- Profile management
- Avatar upload and customization

### Additional Features
- Global state management with Zustand
- Image uploads via Cloudinary
- MongoDB database integration
- RESTful API architecture
- Environment-based configuration

---

## 🛠️ Tech Stack

### Frontend
- **React** - UI library
- **Vite** - Build tool and dev server
- **TailwindCSS** - Utility-first CSS framework
- **DaisyUI** - Component library
- **Zustand** - State management
- **Socket.io Client** - Real-time communication
- **Axios** - HTTP client
- **React Router** - Navigation

### Backend
- **Node.js** - Runtime environment
- **Express** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **Socket.io** - WebSocket library
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Cloudinary** - Image storage
- **Cookie Parser** - Cookie handling
- **Dotenv** - Environment variables

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18.0.0 or higher)
- **npm** (v9.0.0 or higher)
- **MongoDB** (local or Atlas account)
- **Cloudinary Account** (for image uploads)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/chat-app.git
   cd chat-app
   ```

2. **Install dependencies**
   ```bash
   npm run build
   ```
   This will install dependencies for both frontend and backend.

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the `backend` directory:

```env
# Server Configuration
PORT=5001
NODE_ENV=development

# Database
MONGODB_URI=your_mongodb_connection_string

# Authentication
JWT_SECRET=your_super_secret_jwt_key_min_32_characters

# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

### Getting Your Credentials

**MongoDB:**
- Local: `mongodb://localhost:27017/chat-app`
- Atlas: [Get connection string](https://www.mongodb.com/cloud/atlas)

**Cloudinary:**
1. Sign up at [Cloudinary](https://cloudinary.com/)
2. Get credentials from your dashboard

**JWT Secret:**
- Generate a secure random string (minimum 32 characters)
- Example: `openssl rand -base64 32`

---

## 💻 Usage

### Development Mode

**Start Backend:**
```bash
cd backend
npm run dev
```
Backend runs on `http://localhost:5001`

**Start Frontend:**
```bash
cd frontend
npm run dev
```
Frontend runs on `http://localhost:5173`

### Production Mode

**Build and Start:**
```bash
npm run build
npm start
```

### Seed Database (Optional)

To add test users:
```bash
cd backend
node src/seeds/user.seed.js
```

---

## 📁 Project Structure

```
chat-app/
├── backend/
│   ├── src/
│   │   ├── controllers/      # Request handlers
│   │   ├── models/           # Database models
│   │   ├── routes/           # API routes
│   │   ├── middleware/       # Custom middleware
│   │   ├── lib/              # Utilities (DB, Socket, Cloudinary)
│   │   ├── seeds/            # Database seeders
│   │   └── index.js          # Entry point
│   ├── .env                  # Environment variables
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/       # React components
│   │   ├── pages/            # Page components
│   │   ├── store/            # Zustand stores
│   │   ├── lib/              # Utilities
│   │   ├── constants/        # Constants
│   │   └── main.jsx          # Entry point
│   └── package.json
├── .github/                  # GitHub templates
├── CONTRIBUTING.md           # Contribution guidelines
├── CODE_OF_CONDUCT.md        # Code of conduct
├── LICENSE                   # MIT License
├── SECURITY.md               # Security policy
├── CHANGELOG.md              # Version history
└── README.md                 # This file
```

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📧 Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter)

Project Link: [https://github.com/yourusername/chat-app](https://github.com/yourusername/chat-app)

---

## 🙏 Acknowledgments

- [Socket.io Documentation](https://socket.io/docs/)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [React Documentation](https://react.dev/)
- [TailwindCSS](https://tailwindcss.com/)
- [DaisyUI](https://daisyui.com/)
- [Cloudinary](https://cloudinary.com/)

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

Made with ❤️ by [Your Name]

</div>
