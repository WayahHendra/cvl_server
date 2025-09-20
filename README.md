# Locify – Nearby Chat App

[![Node.js](https://img.shields.io/badge/Node.js-20-green?logo=node.js&logoColor=white)](https://nodejs.org)
[![Express](https://img.shields.io/badge/Express-5-black?logo=express&logoColor=white)](https://expressjs.com/)
[![Flutter](https://img.shields.io/badge/Flutter-3.22-blue?logo=flutter&logoColor=white)](https://flutter.dev)
[![Docker](https://img.shields.io/badge/Docker-latest-blue?logo=docker&logoColor=white)](https://www.docker.com/)
[![Redis](https://img.shields.io/badge/Redis-7-orange?logo=redis&logoColor=white)](https://redis.io/)
[![License](https://img.shields.io/badge/License-Apache%202.0-green)](LICENSE)

A modern, scalable, and feature-rich chat application built with **ExpressJS** for the backend and **Flutter** for the frontend.  
The app focuses on **nearby interactions**, allowing users to chat, stream, and build communities with people around them.

## Branding & Vision

### Why "Locify"?

- **"Loc-"** comes from *location* → place, area, proximity.  
- **"-ify"** is a suffix in English that means *to make* or *to create* (e.g., *simplify* = make simple, *beautify* = make beautiful).  
- **Locify** literally means **"to make something location-based"** or **"to localize something"**.

### Contextual Meaning
- 🌍 **Connecting people through location** – making conversations feel more relevant based on where users are.  
- 🏘️ **Building local communities** – strengthening connections between people in the same area.  
- 🌐 **Bringing global experience into a local context** – modern, digital, yet rooted in the user’s surroundings.  

### Branding Impression
- 💡 **Modern & Techy** – the "-ify" suffix gives it a startup vibe (similar to Spotify, Shopify).  
- 🧠 **Easy to remember** – short, 6 letters, simple to pronounce.  
- 🌍 **Global-friendly** – works well internationally, without sounding overly regional.  
- 🔮 **Flexible** – perfect for chat, community, or even future map/location-based features.  

## TODO Roadmap  

- [ ] **Authentication** 
  - Secure login using email & password (credentials)  
  - Social login with Google, Apple, Facebook, Twitter  
  - Token-based authentication with refresh token support  
  - Multi-Factor Authentication (MFA): OTP, email verification, authenticator apps  

- [ ] **Nearby Chat (WebSocket)**  
  - Real-time messaging powered by WebSocket  
  - Ability to delete sent messages  
  - Read receipt indicators for better engagement  

- [ ] **Follow & Recently Viewed Users**  
  - Follow/unfollow other users to build connections  
  - Track recently viewed user profiles  
  - Suggested users based on activity  

- [ ] **File Sender**  
  - Send and receive files within chat  
  - Support for documents, images, audio, and video files  
  - File size limits and security scanning  

- [ ] **Stickers**  
  - Rich communication with sticker packs  
  - Custom and downloadable sticker sets  
  - Integration with chat messages  

- [ ] **Groups & Channels**  
  - Create and manage private/public groups  
  - Channels for one-to-many communication  
  - Role-based permissions for admins and members  

- [ ] **Google Analytics & GTM**  
  - Track user behavior and app performance  
  - Integration with Google Tag Manager for advanced event tracking  
  - Custom analytics dashboards  

- [ ] **System Optimizations**  
  - Performance tuning for better scalability  
  - Reduce latency in real-time communication  
  - Optimize server and database queries  

- [ ] **Streaming Chat – Community (Nearby)**  
  - Real-time group discussions for nearby communities  
  - Public chat streams based on user’s location  
  - Join/leave community streams dynamically  

- [ ] **Voice & Video Call**  
  - One-to-one and group voice calls  
  - High-quality video calls with screen sharing  
  - Call history and notifications  

- [ ] **Nearby Streaming**  
  - Live streaming for nearby audiences  
  - Real-time engagement via comments and reactions  
  - VIP/membership features for boosted visibility
     
## TODO Enhanced Features

- [ ] **User Nearby Maps**  
  - Interactive map showing nearby users  
  - Adjustable distance filters (linked with VIP boost)
  - Integrated with privacy controls & radar system to hide or show location  

- [ ] **VIP – Recommended Nearby Locations**  
  - Basic nearby recommendations with VIP badge  
  - Prioritized visibility for VIP members  

- [ ] **VIP – Customization**  
  - Unlock custom themes  
  - Customize app launcher    

- [ ] **Verified Badge (Influencer Only)**  
  - Available only for influencers with minimum followers on supported social media platforms  
  - Requires membership payment for verification  
  - Badge grants higher trust and visibility across the app  

- [ ] **Radar (17+ only)**  
  - Available only for verified users (17+)  
  - Request by uploading ID Card (KTP) 
  - Location-based radar to find nearby users  

- [ ] **Status & Feed**  
  - Post status updates  
  - Membership-only posting features  

- [ ] **Nearby Distance Limit**  
  - Default: 5KM range  
  - VIP: Boost distance up to 10KM  

- [ ] **Privacy Control**  
  - Option to hide from nearby locations  
  - Manage visibility in maps & radar  

- [ ] **Room Chat & Call**  
  - Create and join private/public chat rooms  
  - Support for voice and video calls within rooms  

- [ ] **Radar Pin**  
  - Set custom pin on radar, only VIP user  
  - Pin represents personal or preferred location  

- [ ] **Interaction Log**  
  - Track user activities & interactions  
  - Useful for moderation and analytics  


## Project Structure  

### Backend (Node.js + Express)  
```
backend/
│── src/
│   ├── config/              # Configuration & environment
│   ├── models/              # Database models (Prisma/Mongoose/Sequelize)
│   ├── controllers/         # Request handlers
│   ├── services/            # Business logic
│   ├── routes/              # Express routes
│   ├── middleware/          # Auth, logging, etc.
│   ├── utils/               # Helpers & utilities
│   └── websocket/           # WebSocket handlers (Socket.IO / ws)
│
│── tests/                   # Unit & integration tests
│── package.json
│── tsconfig.json / jsconfig.json
│── Dockerfile

```

### Frontend (Flutter)  
```
frontend/
│── lib/
│   ├── main.dart
│   ├── core/                # Constants, configs, utils
│   ├── models/              # Data models
│   ├── services/            # API & WebSocket services
│   ├── providers/           # State management (Provider/Bloc)
│   ├── ui/                  
│   │   ├── screens/         # Pages (chat, login, profile, etc.)
│   │   ├── widgets/         # Reusable UI components
│   │   └── themes/          # Theme & styling
│   └── routes.dart
│
│── pubspec.yaml
│── analysis_options.yaml
│── Dockerfile
```

## Description  

This project is a **cross-platform chat application** designed to connect users through **nearby communities**.  
Key features include:  

- 🔐 Authentication (Google, Apple, Facebook, Twitter, etc.)  
- 💬 Real-time chat with WebSocket  
- ✅ Message actions (send, delete for me, delete for everyone, read receipt ✅✅)  
- 📍 Nearby chat & community streams  
- 📎 File sharing & stickers  
- 👥 Groups & channels  
- 📊 Analytics (Google Analytics, GTM)  
- 📹 Future support for calls & video calls  

## Tech Stack  

- **Backend**: Node.js (Express.js), Socket.IO/WebSocket, JWT, OAuth2 
- **Frontend**: Flutter (Dart), Provider/Bloc, WebSocket  
- **Database**: MySQL / MongoDB (choose based on scale)  
- **Cache**: Redis (for sessions & WebSocket scaling)  
- **Containerization**: Docker & Docker Compose  
- **Deployment**: Nginx, Kubernetes (future-ready)  

## System Requirements  

- Node.js ≥ 20  
- Flutter ≥ 3.19  
- Docker ≥ 24.x  
- MySQL ≥ 8 / MongoDB ≥ 6  
- Redis ≥ 7  

## Core Technologies  

- **Node.js / Express.js** – Fast and scalable backend with JavaScript ecosystem  
- **Flutter** – Cross-platform frontend  
- **WebSocket** – Real-time messaging  
- **OAuth 2.0** – Social logins  
- **Docker** – Containerized deployment  

## Installation  

1. Clone repository:
   ```bash
   git clone https://github.com/WayahHendra/locify-nearby-chat-app.git
   cd locify-nearby-chat-app
   ```

2. Setup backend  
   ```bash
   cd backend
   cp .env.example .env
   npm install   # Or pnpm install / yarn install
   ```
   Edit `.env` file with your configuration

3. Setup prisma
   ```bash
   npm run prisma:generate
   npm run prisma:push
   ```

4. Setup frontend  
   ```bash
   cd frontend
   flutter pub get
   flutter run
   ```

## Running the Application  

### Backend (Node.js + Express)
```bash
npm run dev   # For development
npm run build && npm start   # For production
```

### Frontend (Flutter)  
```bash
flutter run -d chrome   # For web
flutter run -d android  # For Android
flutter run -d ios      # For iOS
```

## Testing

Run all tests:
```bash
npm run test
```

Run tests with coverage:
```bash
npm run test:ci
```

## Prisma Commands

| Command                  | Description                            |
|--------------------------|----------------------------------------|
| `npx prisma format`      | Format Prisma schema                   |
| `npx prisma validate`    | Validate Prisma schema                 |
| `npx prisma generate`    | Generate Prisma client                 |
| `npx prisma push`        | Push schema to DB                      |
| `npx prisma migrate dev` | Create migration (keep change history) |
| `npx prisma studio`      | Open Prisma web UI                     |
| `npx prisma seed`        | Seed database                          |

## API Documentation

After running the application in development mode, API documentation is available at:

```
http://localhost:8000/api-docs
```

## Environment Variables  

| Variable                   | Description                             | Example Value                            |
|----------------------------|-----------------------------------------|------------------------------------------|
| `PORT`                     | Backend server port                     | `8000`                                   |
| `APP_NAME`                 | Your app name                           | `-`                                      |
| `APP_VERSION`              | Version Control                         | `1.0.0`                                  |
| `APP_ORIGIN`               | Frontend origin URL                     | `http://localhost:3000`                  |
| `DOMAIN`                   | Backend public base domain              | `http://localhost:5000`                  |
| `BASE_PATH`                | API base path                           | `api/v1`                                 |
| `API_KEY`                  | Secure API key                          | `-`                                      |
| `NODE_ENV`                 | Environment                             | `development/production`                 |
| `DATABASE_URL`             | MongoDB connection URL                  | `mongodb+srv://`                         |
| `REDIS_URL`                | Redis connection string                 | `redis://...`                            |
| `JWT_SECRET`               | JWT secret                              | `-`                                      |
| `JWT_EXPIRES_IN`           | Token expiration                        | `15m`                                    |
| `JWT_REFRESH_SECRET`       | Refresh token secret                    | `-`                                      |
| `OAUTH_GOOGLE_ID`          | Google OAuth client ID                  | `-`                                      |
| `OAUTH_GOOGLE_SECRET`      | Google OAuth secret                     | `-`                                      |
| `OAUTH_APPLE_ID`           | Apple OAuth client ID                   | `-`                                      |
| `OAUTH_FACEBOOK_ID`        | Facebook App ID                         | `-`                                      |
| `OAUTH_TWITTER_ID`         | Twitter API Key                         | `-`                                      |
| `JWT_REFRESH_EXPIRES_IN`   | Refresh token expiration                | `30d`                                    |
| `RESEND_API_KEY`           | Resend API Key                          | `-`                                      |
| `RESEND_FROM_NAME`         | Resend sender name                      | `-`                                      |
| `RESEND_FROM_EMAIL`        | Resend sender email                     | `onboarding@resend.dev`                  |
| `EMAIL_CUSTOMER_SERVICE`   | Email customer service email            | `customer-service@example.com`           |
| `EMAIL_CUSTOMER_SUPPORT`   | Email customer support email            | `customer-support@example.com`           |
| `EMAIL_CUSTOMER_REPORT`    | Email customer report email             | `customer-report@example.com`            |
| `RATE_LIMIT_WINDOW_MS`     | Rate limit window (ms)                  | `900000`                                 |
| `RATE_LIMIT_MAX_PROD`      | Max requests in prod environment        | `100`                                    |
| `RATE_LIMIT_MAX_STAGING`   | Max requests in staging environment     | `300`                                    |
| `RATE_LIMIT_MAX_DEV`       | Max requests in development environment | `10`                                     |
| `RATE_LIMIT_WHITELIST_IPS` | IPs allowed to bypass rate limiting     | `127.0.0.1,10.0.0.1`                     |

## Docker Deployment  

### Backend – `backend/Dockerfile`
```dockerfile
# Backend Dockerfile
FROM node:20-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

FROM node:20-alpine AS runner
WORKDIR /app

COPY package*.json ./
RUN npm install --omit=dev
COPY --from=builder /app/dist ./dist

EXPOSE 3000

CMD ["node", "dist/app.js"]

```

### Frontend – `frontend/Dockerfile`
```dockerfile
# Frontend Dockerfile (Flutter Application)
```

### docker-compose.yml
```yaml
version: "3.9"

services:
  backend:
    build: ./backend
    container_name: chat-backend
    ports:
      - "8080:8080"
    env_file:
      - ./backend/.env
    depends_on:
      - db
      - redis
    restart: unless-stopped

  frontend:
    build: ./frontend
    container_name: chat-frontend
    ports:
      - "3000:80"
    restart: unless-stopped

  db:
    image: mysql:8.4
    container_name: chat-mysql
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: chatdb
      MYSQL_USER: chatapp
      MYSQL_PASSWORD: password
    command: --default-authentication-plugin=mysql_native_password
    ports:
      - "3306:3306"
    volumes:
      - db_data:/var/lib/mysql
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "mysqladmin", "ping", "-h", "localhost"]
      interval: 10s
      timeout: 5s
      retries: 5

  redis:
    image: redis:7
    container_name: chat-redis
    ports:
      - "6379:6379"
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 10s
      timeout: 5s
      retries: 5

volumes:
  db_data:

```

## Documentation & Policies

For detailed information on project management, security, and conduct, please refer to the following documents:

* **Code of Conduct** – [CODE\_OF\_CONDUCT.md](./CONTRIBUTING.md)
* **Security Guidelines** – [SECURITY.md](./SECURITY.md)
* **Version Control Policy** – [VERSION\_CONTROL.md](./VERSION_CONTROL.md)
* **Changelog** – [CHANGELOG.md](./CHANGELOG.md)

## 🤝 Contributing

Please refer to the **Version Control Policy** for detailed instructions on contributing: [VERSION\_CONTROL.md](./VERSION_CONTROL.md).

## License

This project is licensed under the **Apache License 2.0** – see the [LICENSE](LICENSE) file for details.
