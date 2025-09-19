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

- [ ] **Authentication** – Google, Apple, Facebook, Twitter  
- [ ] **Nearby Chat (WebSocket)** – send, delete, read receipt  
- [ ] **Follow & Recently Viewed Users**  
- [ ] **File Sender**  
- [ ] **Stickers**  
- [ ] **Groups & Channels**  
- [ ] **Google Analytics & GTM**  
- [ ] **System Optimizations**  
- [ ] **Streaming Chat – Community (Nearby)**  
- [ ] **Voice & Video Call**  
- [ ] **User Nearby Maps**  
- [ ] **Nearby Streaming**  

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

### Backend  
```bash
cd backend
cp .env.example .env
npm install   # Or pnpm install / yarn install
npm run dev   # For development
npm run build && npm start   # For production
```

### Frontend  
```bash
cd frontend
flutter pub get
flutter run
```

## Running the Application  

### Backend (Node.js + Express)
```bash
npm run dev
```

### Frontend (Flutter)  
```bash
flutter run -d chrome   # For web
flutter run -d android  # For Android
flutter run -d ios      # For iOS
```

## Testing  

### Backend  
```bash
npm test
```

### Frontend  
```bash
flutter test
```

## Environment Variables  

| Variable              | Description                               | Default Value      |
|-----------------------|-------------------------------------------|--------------------|
| `PORT`                | Backend server port                       | `8080`             |
| `DB_URL`              | Database connection string                | `postgres://...`   |
| `REDIS_URL`           | Redis connection string                   | `redis://...`      |
| `JWT_SECRET`          | Secret key for JWT auth                   | `changeme`         |
| `OAUTH_GOOGLE_ID`     | Google OAuth client ID                    | `-`                |
| `OAUTH_GOOGLE_SECRET` | Google OAuth secret                       | `-`                |
| `OAUTH_APPLE_ID`      | Apple OAuth client ID                     | `-`                |
| `OAUTH_FACEBOOK_ID`   | Facebook App ID                           | `-`                |
| `OAUTH_TWITTER_ID`    | Twitter API Key                           | `-`                |
| `FRONTEND_URL`        | Flutter Web / Mobile URL                  | `http://localhost` |

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
