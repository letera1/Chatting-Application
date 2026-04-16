# Contributing to Full Stack Realtime Chat App

First off, thank you for considering contributing to this project! It's people like you that make this chat application better for everyone.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Process](#development-process)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed and what you expected**
- **Include screenshots if possible**
- **Include your environment details** (OS, Node version, browser, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Explain why this enhancement would be useful**
- **List any similar features in other applications if applicable**

### Your First Code Contribution

Unsure where to begin? You can start by looking through `beginner` and `help-wanted` issues:

- **Beginner issues** - issues which should only require a few lines of code
- **Help wanted issues** - issues which should be a bit more involved

## Getting Started

1. **Fork the repository** and clone your fork
   ```bash
   git clone https://github.com/your-username/chat-app.git
   cd chat-app
   ```

2. **Install dependencies**
   ```bash
   npm run build
   ```

3. **Set up environment variables**
   - Copy `.env.example` to `.env` in the backend folder
   - Fill in your MongoDB URI, JWT secret, and Cloudinary credentials

4. **Create a new branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Development Process

1. **Make your changes** in your feature branch
2. **Test your changes** thoroughly
3. **Commit your changes** with clear, descriptive commit messages
   ```bash
   git commit -m "Add feature: description of your feature"
   ```

### Running the Application

**Development mode:**
```bash
# Backend (from backend folder)
npm run dev

# Frontend (from frontend folder)
npm run dev
```

**Production mode:**
```bash
npm start
```

## Pull Request Process

1. **Update documentation** if you're changing functionality
2. **Ensure all tests pass** and the app runs without errors
3. **Update the README.md** with details of changes if applicable
4. **Follow the PR template** and provide a clear description
5. **Link any related issues** in your PR description
6. **Request review** from maintainers
7. **Address review comments** promptly

### PR Title Format

Use conventional commit format:
- `feat: add new feature`
- `fix: resolve bug in authentication`
- `docs: update installation instructions`
- `style: format code with prettier`
- `refactor: restructure message controller`
- `test: add tests for user model`
- `chore: update dependencies`

## Style Guidelines

### JavaScript Style Guide

- Use **ES6+ syntax** (arrow functions, destructuring, etc.)
- Use **meaningful variable names**
- Add **comments for complex logic**
- Follow **existing code patterns** in the project
- Use **async/await** instead of promises where possible

### Git Commit Messages

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests after the first line

### Code Formatting

- Use **2 spaces** for indentation
- Use **semicolons**
- Use **single quotes** for strings
- Add **trailing commas** in multi-line objects/arrays

## Project Structure

```
├── backend/
│   ├── src/
│   │   ├── controllers/    # Request handlers
│   │   ├── models/         # Database models
│   │   ├── routes/         # API routes
│   │   ├── middleware/     # Custom middleware
│   │   └── lib/            # Utilities and configs
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Page components
│   │   ├── store/          # Zustand state management
│   │   └── lib/            # Utilities
│   └── package.json
└── README.md
```

## Questions?

Feel free to open an issue with your question or reach out to the maintainers.

## Recognition

Contributors will be recognized in our README.md file. Thank you for your contributions!

---

**Happy Contributing! 🚀**
