# 🔐 OAuth2 Auth Service

<p align="center">
  <img src="https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=spring-security&logoColor=white" />
  <img src="https://img.shields.io/badge/OAuth2-EB5424?style=for-the-badge&logo=auth0&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</p>

> A **production-ready OAuth2 Authorization Server** built with Spring Security and Spring Authorization Server. Supports multiple identity providers, fine-grained RBAC, JWT access tokens, and refresh token rotation.

---

## ✨ Features

- 🔐 **OAuth2 Authorization Server** — Full OAuth2.0 + OIDC implementation with Spring Authorization Server
- 🪙 **JWT Tokens** — Signed access tokens with RSA key pairs, customizable claims
- 🔄 **Refresh Token Rotation** — Secure refresh token management with Redis
- 👥 **Social Login** — Google, GitHub, and Microsoft OAuth2 providers
- 🏷️ **Role-Based Access Control (RBAC)** — Fine-grained roles and permissions
- 🔒 **MFA Support** — TOTP-based two-factor authentication
- 📋 **User Management API** — Full CRUD for users, roles, and permissions
- 🛡️ **Rate Limiting** — Per-user and per-IP login attempt throttling
- 📊 **Audit Logging** — Complete login/logout and token event audit trail
- 🐳 **Docker Ready** — Single docker-compose for full local setup

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Language | Java 17 |
| Framework | Spring Boot 3.2 |
| Security | Spring Security 6 + Spring Authorization Server |
| Token Format | JWT (RSA-256 signed) |
| Social OAuth | Google, GitHub, Microsoft |
| Session/Token Store | Redis 7 |
| Database | PostgreSQL 15 |
| MFA | TOTP (Google Authenticator compatible) |
| Containerization | Docker + Docker Compose |

---

## 🚀 Quick Start

```bash
git clone https://github.com/Chanduveldi2211/oauth2-auth-service.git
cd oauth2-auth-service
docker-compose up -d

# Authorization Server: http://localhost:9000
# OIDC Discovery:       http://localhost:9000/.well-known/openid-configuration
```

---

## 🔑 OAuth2 Flow

```
Client → Authorization Request → /oauth2/authorize
       ← Authorization Code
Client → Token Request → /oauth2/token (with code + PKCE)
       ← Access Token (JWT) + Refresh Token
Client → Protected API → Authorization: Bearer {token}
API    → Token Introspection / JWT Validation
       ← 200 OK / 401 Unauthorized
```

---

## 📁 Project Structure

```
oauth2-auth-service/
├── src/main/java/com/chanduveldi/auth/
│   ├── config/
│   │   ├── AuthorizationServerConfig.java
│   │   ├── SecurityConfig.java
│   │   └── TokenConfig.java
│   ├── controller/
│   │   ├── UserController.java
│   │   └── AuthController.java
│   ├── service/
│   │   ├── UserDetailsServiceImpl.java
│   │   ├── TokenService.java
│   │   └── MfaService.java
│   └── model/
│       ├── User.java
│       └── Role.java
└── docker-compose.yml
```

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

<p align="center">Made with ❤️ by <a href="https://github.com/Chanduveldi2211">Veldi Purna Chandu</a> | Senior Software Engineer</p>
