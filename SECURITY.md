# Security Policy

## Supported Versions

We release patches for security vulnerabilities. Currently supported versions:

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Reporting a Vulnerability

We take the security of our chat application seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### Please do NOT:

- Open a public GitHub issue for security vulnerabilities
- Disclose the vulnerability publicly before it has been addressed

### Please DO:

1. **Email us directly** with details of the vulnerability
2. **Provide detailed information** including:
   - Type of vulnerability (e.g., XSS, SQL injection, authentication bypass)
   - Full paths of source file(s) related to the vulnerability
   - Location of the affected source code (tag/branch/commit or direct URL)
   - Step-by-step instructions to reproduce the issue
   - Proof-of-concept or exploit code (if possible)
   - Impact of the vulnerability

### What to expect:

- **Acknowledgment**: We will acknowledge receipt of your vulnerability report within 48 hours
- **Updates**: We will send you regular updates about our progress
- **Timeline**: We aim to address critical vulnerabilities within 7 days
- **Credit**: If you wish, we will publicly acknowledge your responsible disclosure

## Security Best Practices for Users

### Environment Variables

Never commit your `.env` file to version control. It contains sensitive information:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
```

### JWT Secret

- Use a strong, random JWT secret (minimum 32 characters)
- Never share your JWT secret
- Rotate your JWT secret periodically

### Database Security

- Use strong MongoDB credentials
- Enable MongoDB authentication
- Use connection strings with authentication
- Restrict database access to specific IP addresses when possible

### Cloudinary Security

- Keep your Cloudinary API credentials secure
- Use signed uploads when possible
- Set up upload presets with restrictions

### HTTPS

- Always use HTTPS in production
- Never send sensitive data over HTTP
- Use secure cookies for authentication tokens

### Dependencies

- Regularly update dependencies to patch known vulnerabilities
- Run `npm audit` to check for vulnerabilities
- Use `npm audit fix` to automatically fix issues when possible

## Known Security Considerations

### Authentication

- JWT tokens are stored in localStorage (consider httpOnly cookies for enhanced security)
- Tokens expire after a set period
- Passwords are hashed using bcrypt

### Input Validation

- All user inputs are validated on both client and server
- MongoDB queries use parameterized queries to prevent injection
- File uploads are validated for type and size

### Rate Limiting

Consider implementing rate limiting for:
- Login attempts
- Message sending
- File uploads
- API requests

### CORS

- Configure CORS properly for your production domain
- Don't use wildcard (*) in production

## Security Updates

We will announce security updates through:
- GitHub Security Advisories
- Release notes
- README updates

## Compliance

This application handles user data. Ensure you comply with:
- GDPR (if serving EU users)
- CCPA (if serving California users)
- Other relevant data protection regulations

---

Thank you for helping keep our application and users safe!
