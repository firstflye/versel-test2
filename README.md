# OKCode - Instagram-like Social Media Platform

OKCode is a modern social media platform inspired by Instagram, built with React, Node.js, Express, and MySQL. It features user profiles, photo/video sharing, likes, comments, stories, and more.

## Features

- User authentication (login/registration)
- Photo and video sharing
- Stories that expire after 24 hours
- Reels (short videos)
- Like and comment functionality
- User profiles with followers/following
- Responsive design (mobile & desktop)
- Dark mode support

## Requirements

- Node.js 18+
- MySQL database (XAMPP recommended for local development)

## Setup

1. Clone the repository
2. Install dependencies:
   ```
   npm install
   ```
3. Start XAMPP (or your MySQL server)
4. Set up the database:
   ```
   node install-database.js
   ```
5. Start the development server:
   ```
   npm run dev
   ```

## Database Integration

The application supports both in-memory storage (for development) and MySQL database storage. By default, it will try to connect to a MySQL database first and fall back to in-memory if not available.

### MySQL Configuration

The default MySQL configuration is:
```
host: 'localhost'
user: 'root'
password: ''
database: 'okcode_db'
```

You can modify these settings in the `server/database.ts` file if needed.

### Database Schema

The application uses the following tables:
- `users` - User accounts
- `posts` - Posts (images with captions)
- `likes` - Post likes
- `comments` - Post comments
- `follows` - User follow relationships
- `stories` - User stories (24-hour expiry)
- `reels` - Short videos
- `sessions` - Express session storage

## Storage Providers

The application has two storage providers:

1. **MemStorage** - In-memory storage using JavaScript Maps
2. **MySQLStorage** - Persistent storage using MySQL

The system automatically chooses the appropriate storage provider based on database availability.

## Authentication

Authentication is implemented using Passport.js with a local strategy. Passwords are securely hashed using Node.js's crypto module with scrypt.

## File Storage

For development, files (images and videos) are stored as base64 data URLs. In a production environment, you would typically use a cloud storage service like AWS S3 or Azure Blob Storage.

## Development

During development, run:
```
npm run dev
```

This starts both the backend Express server and the frontend Vite development server.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.