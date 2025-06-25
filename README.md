# 🧰 Product Manager – Fullstack Application

Ce projet est une application complète de gestion de produits composée de :

- 🔙 Un backend Spring Boot sécurisé avec JWT
- 💻 Un frontend React + Vite + TypeScript
- 🐳 Une infrastructure Docker pour exécution locale ou déploiement

---

## 🧠 Backend – `product-manager`

### 📚 Technologies

- Java 17
- Spring Boot 3
- Spring Security + JWT
- PostgreSQL + Hibernate
- Spring Data JPA
- Docker

### ▶️ Lancement local

```bash
cd product-manager
./gradlew bootRun
```

### 📦 Build JAR

```bash
./gradlew clean build
```

### 📂 API principale

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| POST | /api/products | Ajouter un produit |
| GET | /api/products | Liste des produits |
| GET | /api/products/{id} | Détail d'un produit |
| PUT | /api/products/{id} | Modifier un produit |
| DELETE | /api/products/{id} | Supprimer un produit |

### 🔐 Endpoints d'authentification :

- POST /api/auth/register
- POST /api/auth/login

JWT est requis pour les appels sécurisés (via Authorization: Bearer <token>).

---

## 💻 Frontend – product-manager-ui

### ⚙️ Technologies

- React + Vite + TypeScript
- React Router
- Axios
- TailwindCSS
- Nginx (prod)

### ▶️ Lancer en développement

```bash
cd product-manager-ui
npm install
npm run dev
```

Accessible via : http://localhost:5173

### 🔧 Configuration Proxy (vite.config.ts)

```ts
server: {
  proxy: {
    '/api': {
      target: 'http://localhost:8080',
      changeOrigin: true
    }
  }
}
```

---

## 🐳 Docker & Docker Compose

Le projet est containerisé avec 3 services :

- frontend (React + Nginx)
- backend (Spring Boot)
- db (PostgreSQL)

### ▶️ Lancer le tout

```bash
docker-compose up --build
```

- Frontend : http://localhost:5173
- Backend : http://localhost:8080
- PostgreSQL : localhost:5432 (user: postgres, pwd: 2002)

---

## 🧪 Tests

```bash
cd product-manager
./gradlew test
```

---

## ✅ Prérequis

- Docker & Docker Compose
- Java 17
- Node.js 20+

---

## 📁 Structure

```
product-manager/
├── docker-compose.yml
├── product-manager/        ← Backend
└── product-manager-ui/     ← Frontend
```

## 👨‍💻 Auteur

Développé par :

**Youssef Achkir**

- 🔗 [LinkedIn](https://www.linkedin.com/in/youssef-achkir/)
- 💻 [GitHub](https://github.com/youssef2002-achkir)
