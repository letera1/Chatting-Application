# Frequently Asked Questions (FAQ)

## Table of Contents

- [General Questions](#general-questions)
- [Installation & Setup](#installation--setup)
- [Configuration](#configuration)
- [Features](#features)
- [Troubleshooting](#troubleshooting)
- [Development](#development)
- [Deployment](#deployment)
- [Contributing](#contributing)

---

## General Questions

### What is this project?

This is a full-stack real-time chat application built with the MERN stack (MongoDB, Express, React, Node.js) and Socket.io for real-time communication.

### What features does it include?

- Real-time messaging
- User authentication (JWT)
- Online/offline status
- Image sharing
- Profile management
- Theme customization
- Responsive design

### Is this project free to use?

Yes! This project is open-source and licensed under the MIT License. You can use it for personal or commercial projects.

### Can I use this for my portfolio?

Absolutely! This project is perfect for showcasing your full-stack development skills.

---

## Installation & Setup

### What are the prerequisites?

- Node.js (v18.0.0 or higher)
- npm (v9.0.0 or higher)
- MongoDB (local installation or Atlas account)
- Cloudinary account (for image uploads)

### How do I install the project?

```bash
git clone https://github.com/yourusername/chat-app.git
cd chat-app
npm run build
```

### Do I need to install frontend and backend separately?

No, running `npm run build` from the root directory installs dependencies for both frontend and backend.

### How long does installation take?

Typically 2-5 minutes depending on your internet connection.

---

## Configuration

### Where do I put my environment variables?

Create a `.env` file in the `backend` directory. Use `backend/.env.example` as a template.

### How do I get a MongoDB connection string?

**Local MongoDB:**
```
mongodb://localhost:27017/chat-app
```

**MongoDB Atlas:**
1. Sign up at [mongodb.com/cloud/atlas](https://www.mongodb.com/cloud/atlas)
2. Create a cluster
3. Click "Connect" → "Connect your application"
4. Copy the connection string

### How do I get Cloudinary credentials?

1. Sign up at [cloudinary.com](https://cloudinary.com/)
2. Go to your dashboard
3. Copy Cloud Name, API Key, and API Secret

### How do I generate a JWT secret?

Use a random string generator or run:
```bash
openssl rand -base64 32
```

### What ports does the app use?

- Backend: `5001` (configurable via PORT in .env)
- Frontend (dev): `5173` (Vite default)

---

## Features

### Can users send images?

Yes! Users can upload and share images in messages via Cloudinary.

### Is there a group chat feature?

Not yet, but it's on the [roadmap](ROADMAP.md) for v2.0.0.

### Can I change the theme?

Yes! The app includes 29+ themes from DaisyUI. Users can switch themes in the Settings page.

### Are messages encrypted?

Currently, messages are stored in plain text. End-to-end encryption is planned for v2.2.0.

### Can users delete messages?

Not yet, but message deletion is planned for v1.1.0.

### Is there a mobile app?

Currently, it's a responsive web app. A mobile app (React Native) is planned for v2.3.0.

---

## Troubleshooting

### The app won't start. What should I check?

1. Ensure all dependencies are installed: `npm run build`
2. Check your `.env` file exists and has correct values
3. Verify MongoDB is running (if using local)
4. Check if ports 5001 and 5173 are available
5. Look for error messages in the console

### I get "Cannot connect to MongoDB"

**Solutions:**
- Verify your `MONGODB_URI` in `.env`
- Check if MongoDB service is running (local)
- Verify network access in MongoDB Atlas
- Check firewall settings

### Images won't upload

**Solutions:**
- Verify Cloudinary credentials in `.env`
- Check image file size (max 10MB)
- Ensure image format is supported (JPG, PNG, GIF)
- Check browser console for errors

### Real-time messages aren't working

**Solutions:**
- Check if Socket.io is connected (browser console)
- Verify backend is running
- Check for CORS issues
- Clear browser cache and cookies

### I get "JWT token invalid"

**Solutions:**
- Clear cookies and login again
- Verify `JWT_SECRET` in `.env`
- Check if token has expired
- Restart the backend server

### Frontend shows blank page

**Solutions:**
- Check browser console for errors
- Verify backend is running
- Clear browser cache
- Rebuild frontend: `cd frontend && npm run build`

---

## Development

### How do I run in development mode?

**Backend:**
```bash
cd backend
npm run dev
```

**Frontend:**
```bash
cd frontend
npm run dev
```

### How do I add test users?

```bash
cd backend
node src/seeds/user.seed.js
```

### Can I use TypeScript?

The project currently uses JavaScript. TypeScript migration is on the roadmap.

### How do I add a new feature?

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### How do I run tests?

Tests are not yet implemented. Adding tests is on the roadmap.

---

## Deployment

### Where can I deploy this app?

**Backend:**
- Render
- Railway
- Heroku
- DigitalOcean
- AWS

**Frontend:**
- Vercel
- Netlify
- Render
- GitHub Pages (with backend separately)

### How do I deploy to production?

1. Set `NODE_ENV=production` in your hosting platform
2. Configure environment variables
3. Build the frontend: `npm run build`
4. Deploy backend and frontend
5. Update CORS settings for your domain

### Do I need separate hosting for frontend and backend?

Not necessarily. You can:
- Host both together (serve frontend from backend)
- Host separately (recommended for scaling)

### What about the database in production?

Use MongoDB Atlas (free tier available) instead of local MongoDB.

### How much does deployment cost?

Many platforms offer free tiers:
- MongoDB Atlas: Free (512MB)
- Cloudinary: Free (25 credits/month)
- Render: Free tier available
- Vercel/Netlify: Free for personal projects

---

## Contributing

### How can I contribute?

See our [CONTRIBUTING.md](CONTRIBUTING.md) guide for detailed instructions.

### I found a bug. What should I do?

1. Check if it's already reported in [Issues](https://github.com/yourusername/chat-app/issues)
2. If not, create a new issue using the bug report template
3. Provide detailed information and steps to reproduce

### I have a feature idea

Great! Submit a feature request using our [feature request template](https://github.com/yourusername/chat-app/issues/new?template=feature_request.md).

### Do I need permission to fork this project?

No! This is open-source. Fork away and make it your own.

### Will my contributions be credited?

Yes! All contributors are recognized in the project.

---

## Still Have Questions?

- 📧 Email: your-email@example.com
- 💬 Discord: [Join our server](#)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/chat-app/issues)
- 📖 Docs: [Full Documentation](ARCHITECTURE.md)

---

**Last Updated:** January 2024
