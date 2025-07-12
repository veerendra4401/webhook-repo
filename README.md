# GitHub Webhook Monitor

A real-time dashboard for monitoring GitHub repository events with a beautiful dark mode UI.

![GitHub Dark Mode Theme](https://img.shields.io/badge/theme-GitHub%20Dark-0d1117)
![MongoDB](https://img.shields.io/badge/database-MongoDB-47A248)
![Flask](https://img.shields.io/badge/backend-Flask-000000)

## Features

### Backend
- 🔒 Secure webhook endpoint with HMAC signature verification
- 📦 MongoDB integration for persistent storage
- 🌐 RESTful API for event retrieval
- 🕒 Automatic timezone conversion to IST
- ✨ Support for multiple event types:
  - Push events
  - Pull Request events
  - Merge events

### Frontend
- 🎨 GitHub-themed dark mode UI
- ⚡ Real-time event monitoring (15s polling)
- 🔄 Manual refresh with loading animation
- 📊 Event count and statistics
- 📱 Fully responsive design
- 🎯 Event-specific icons and styling
- ⏰ Last refresh time indicator

## Tech Stack

- **Backend**: Python Flask
- **Database**: MongoDB
- **Frontend**: Vanilla JavaScript, CSS3
- **Security**: HMAC SHA-1
- **Deployment**: Development Server

## Setup

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Configure environment variables in `.env`:
   ```env
   MONGODB_URI=your_mongodb_connection_string
   GITHUB_SECRET=your_webhook_secret
   DATABASE_NAME=github_events
   COLLECTION_NAME=events
   ```

3. Configure GitHub webhook:
   - Go to repository settings → Webhooks → Add webhook
   - Payload URL: `http://your-domain/webhook`
   - Content type: `application/json`
   - Secret: Same as `GITHUB_SECRET` in `.env`
   - Events: Select `Push` and `Pull requests`

4. Start the application:
   ```bash
   python app.py
   ```

## Event Types

| Event | Description | Icon |
|-------|-------------|------|
| Push | When code is pushed to any branch | 🔵 |
| Pull Request | When a PR is opened or updated | 🟢 |
| Merge | When a PR is approved and merged | 🟣 |

## Security Features

- HMAC signature verification for webhooks
- Environment-based configuration
- Input validation and sanitization
- Error handling and logging
- Rate limiting protection

## Development

The application is currently in development mode. For production:
- Use a production WSGI server
- Set up proper MongoDB authentication
- Configure HTTPS
- Implement rate limiting
- Add monitoring and logging

## Contributing

Feel free to open issues or submit pull requests. All contributions are welcome!

## License

MIT License - feel free to use this project for your own purposes. 