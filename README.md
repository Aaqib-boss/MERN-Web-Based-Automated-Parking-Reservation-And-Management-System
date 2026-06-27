# ParkSmart - Premium IoT Smart Parking Solution

ParkSmart is a premium, real-time, IoT-enabled parking reservation and management platform designed to streamline parking slot allocation, pricing customizations, and administrative operations across multiple geographic branches.

---

## 🌐 Live Demo

| Portal | URL |
|---|---|
| **Customer Portal** | [mern-web-based-automated-parking-re.vercel.app](https://mern-web-based-automated-parking-re.vercel.app) |
| **Operations Admin** | [mern-web-based-automated-parking-re-eight.vercel.app](https://mern-web-based-automated-parking-re-eight.vercel.app) |
| **Super Admin** | [parking-super-admin.vercel.app](https://parking-super-admin.vercel.app) |
| **Backend API** | [parking-system-backend-amgk.onrender.com](https://parking-system-backend-amgk.onrender.com) |

---

## 🔐 Demo Login Credentials

| Role | Email | Password |
|---|---|---|
| **Super Admin** | `super@parking.com` | `password123` |
| **Operations Admin** | `ops@parking.com` | `password123` |
| **Customer** | `john@gmail.com` | `password123` |

---

## 🌟 Key Features

### 1. Per-Branch Isolation & Dynamic Scaling
- **Independent Capacity Grids**: Automatically spawns 60 default floor slots (Ground, 1st, 2nd floors) for any brand-new branch on the fly.
- **Per-Branch Analytics**: Track revenue metrics, occupancy rates, and transaction trends separately for every branch.
- **Compound Database Constraints**: Compound unique indexes `{ spotNumber: 1, branch: 1 }` enable identical slot identifiers (e.g. `G-01`) to coexist across branches.

### 2. Interactive Location Maps & Contacts
- **Branch Customizations**: Super Admins can customize separate physical addresses, phone numbers, emails, and Google Maps embed/share links for each branch.
- **Collapsible Live Previews**: Users on the Parking Map can toggle a collapsible branch details card to preview specific location details and interactive Google Maps iframes.
- **Dynamic Footer Selector**: Clicking on any branch under "Our Branches" in the footer instantly updates the address, email, phone, and embedded map location dynamically.

### 3. Real-Time Status Broadcasts
- **IoT-Sensor Sync**: Socket.io integration pushes instant updates to all clients when a slot status toggles (Available, Occupied, Reserved).
- **Automated Pricing Calculations**: Fetches and applies branch-specific hourly rate models (Base, 2 Hour, 4 Hour, and Full Day rates) at booking checkout.

---

## 📂 Project Architecture
smart-parking/

├── server/             # Express server, MongoDB schemas, seeder, socket logic

├── client-user/        # Customer booking portal (http://localhost:5173/)

├── client-ops/         # Operations Admin dashboard (http://localhost:5174/)

└── client-super/       # Super Admin settings & user panel (http://localhost:5175/)

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
