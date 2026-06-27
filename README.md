### Tech Stack
- **Backend**: Node.js, Express, MongoDB (Mongoose ODM), Socket.io (WebSockets)
- **Frontends**: React (Vite), Axios, Recharts (Analytical Charts), Lucide Icons, Vanilla CSS
- **Hosting**: Vercel (Frontend) + Render (Backend) + MongoDB Atlas (Database)

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v16+ recommended)
- [MongoDB](https://www.mongodb.com/) (running locally or via Atlas connection)

### 1. Installation
Install dependencies in the server and all client directories:

```bash
# Backend
cd server && npm install

# User Client
cd ../client-user && npm install

# Operations Client
cd ../client-ops && npm install

# Super Admin Client
cd ../client-super && npm install
```

### 2. Environment Setup
Create a `.env` file in the `server` directory:

```env
PORT=5000
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:5173
CLIENT_OPS_URL=http://localhost:5174
CLIENT_SUPER_URL=http://localhost:5175
SIMULATE_PAYMENTS=true
```

### 3. Database Initialization
Run the database seeder to populate default user accounts, configuration settings, and the Negombo branch's capacity slots:

```bash
cd server
npm run seed
```

### 4. Run Development Servers

```bash
# Start Backend (runs on http://localhost:5000/)
cd server && npm run dev

# Start User Portal (runs on http://localhost:5173/)
cd client-user && npm run dev

# Start Operations Admin Portal (runs on http://localhost:5174/)
cd client-ops && npm run dev

# Start Super Admin Portal (runs on http://localhost:5175/)
cd client-super && npm run dev
```

---

## ☁️ Production Deployment

| Service | Platform |
|---|---|
| Frontend (3 portals) | Vercel |
| Backend API | Render |
| Database | MongoDB Atlas |
