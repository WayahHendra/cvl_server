# 💬 Locify – Nearby Chat App

[![Go](https://img.shields.io/badge/Go-1.22-blue?logo=go&logoColor=white)](https://golang.org)
[![Flutter](https://img.shields.io/badge/Flutter-3.22-blue?logo=flutter&logoColor=white)](https://flutter.dev)
[![Docker](https://img.shields.io/badge/Docker-latest-blue?logo=docker&logoColor=white)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Build](https://img.shields.io/github/actions/workflow/status/your-org/chat-app/ci.yml?branch=main)](https://github.com/your-org/chat-app/actions)

A modern, scalable, and feature-rich chat application built with **Golang** for the backend and **Flutter** for the frontend.  
The app focuses on **nearby interactions**, allowing users to chat, stream, and build communities with people around them.

## 🌟 Branding & Vision

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

## ✅ TODO Roadmap  

- [ ] **Authentication** – Google, Apple, Facebook, Twitter (v1.0.0)  
- [ ] **Nearby Chat (WebSocket)** – send, delete, read receipt (v1.0.0)  
- [ ] **Follow & Recently Viewed Users** (v1.1.0)  
- [ ] **File Sender** (v1.2.0)  
- [ ] **Stickers** (v1.3.0)  
- [ ] **Groups & Channels** (v1.4.0)  
- [ ] **Google Analytics & GTM** (v1.5.0)  
- [ ] **System Optimizations** (v1.6.1)  
- [ ] **Streaming Chat – Community (Nearby)** (v2.0.0)  
- [ ] **Voice & Video Call** (v3.0.0)  
- [ ] **User Nearby Maps** (v4.0.0)  
- [ ] **Nearby Streaming** (v5.0.0)  

## 📂 Project Structure  

### Backend (Go)  
```
backend/
│── cmd/
│   └── server/              # Entry point for API server
│       └── main.go
│
│── internal/
│   ├── config/              # Configuration & environment
│   ├── models/              # Data models
│   ├── handlers/            # HTTP & WebSocket handlers
│   ├── services/            # Business logic
│   ├── repository/          # Database layer
│   ├── middleware/          # Middlewares (auth, logging, etc.)
│   ├── utils/               # Helpers & utilities
│   └── websocket/           # WebSocket hub & connections
│
│── pkg/                     # Shared packages (JWT, OAuth, etc.)
│── go.mod
│── go.sum
│── Dockerfile
│── Makefile
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

## 📝 Description  

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

## ⚙️ Tech Stack  

- **Backend**: Go (Golang), Gin/Fiber, WebSocket, JWT, OAuth2  
- **Frontend**: Flutter (Dart), Provider/Bloc, WebSocket  
- **Database**: MySQL / MongoDB (choose based on scale)  
- **Cache**: Redis (for sessions & WebSocket scaling)  
- **Containerization**: Docker & Docker Compose  
- **Deployment**: Nginx, Kubernetes (future-ready)  

## 🖥️ System Requirements  

- Go ≥ 1.22  
- Flutter ≥ 3.19  
- Docker ≥ 24.x  
- MySQL ≥ 8 / MongoDB ≥ 6  
- Redis ≥ 7  

## 🔑 Core Technologies  

- **Go** – High performance backend  
- **Flutter** – Cross-platform frontend  
- **WebSocket** – Real-time messaging  
- **OAuth 2.0** – Social logins  
- **Docker** – Containerized deployment  

## 🚀 Installation  

### Backend  
```bash
cd backend
cp .env.example .env
go mod tidy
go run cmd/server/main.go
```

### Frontend  
```bash
cd frontend
flutter pub get
flutter run
```

## ▶️ Running the Application  

### Backend (Go)  
```bash
make run
```

### Frontend (Flutter)  
```bash
flutter run -d chrome   # For web
flutter run -d android  # For Android
flutter run -d ios      # For iOS
```

## 🧪 Testing  

### Backend  
```bash
go test ./...
```

### Frontend  
```bash
flutter test
```

## 🌍 Environment Variables  

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

## 🐳 Docker Deployment  

### Backend – `backend/Dockerfile`
```dockerfile
# Backend Dockerfile
FROM golang:1.22 AS builder

WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download

COPY . .
RUN go build -o chatapp ./cmd/server

FROM debian:bookworm-slim
WORKDIR /root/
COPY --from=builder /app/chatapp .
COPY .env .env
EXPOSE 8080
CMD ["./chatapp"]
```

### Frontend – `frontend/Dockerfile`
```dockerfile
# Frontend Dockerfile (Flutter Web)
FROM cirrusci/flutter:3.19.6 AS build

WORKDIR /app
COPY . .
RUN flutter pub get
RUN flutter build web

FROM nginx:alpine
COPY --from=build /app/build/web /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### docker-compose.yml
```yaml
version: "3.9"
services:
  backend:
    build: ./backend
    ports:
      - "8080:8080"
    env_file:
      - ./backend/.env
    depends_on:
      - db
      - redis

  frontend:
    build: ./frontend
    ports:
      - "3000:80"

  db:
    image: postgres:14
    environment:
      POSTGRES_USER: chatapp
      POSTGRES_PASSWORD: password
      POSTGRES_DB: chatdb
    ports:
      - "5432:5432"

  redis:
    image: redis:7
    ports:
      - "6379:6379"
```

## 📝 Documentation & Policies

For detailed information on project management, security, and conduct, please refer to the following documents:

* **Code of Conduct** – [CODE\_OF\_CONDUCT.md](./CONTRIBUTING.md)
* **Security Guidelines** – [SECURITY.md](./SECURITY.md)
* **Version Control Policy** – [VERSION\_CONTROL.md](./VERSION_CONTROL.md)

## 🤝 Contributing

Please refer to the **Version Control Policy** for detailed instructions on contributing: [VERSION\_CONTROL.md](./VERSION_CONTROL.md).

## 📜 License

This project is licensed under the **Apache License 2.0** – see the [LICENSE](LICENSE) file for details.
