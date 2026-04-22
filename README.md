# TapaRide Backend API

Node.js/Express REST API for TapaRide with authentication, authorization, and booking system support.

---



---

## ⚙️ Setup Instructions

### 1. Clone the project
```bash
git clone https://github.com/Zzawadii/TapaRide.git
cd TapaRide/backend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Create environment file
Create a `.env` file in the backend folder:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/taparide
JWT_SECRET=your_secret_key
JWT_EXPIRE=7d
NODE_ENV=development
```

### 4. Start MongoDB
Make sure MongoDB is running locally:
```bash
mongod
```

### 5. Run the server
```bash
npm run dev
```

Server runs on: **http://localhost:5000**

---

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register` → Register new user
- `POST /api/auth/login` → Login user
- `GET /api/auth/me` → Get current user (protected)
- `PUT /api/auth/updatepassword` → Update password (protected)

### Bookings (Demo)
- `GET /api/bookings/my-bookings` → Get user bookings (protected)
- `POST /api/bookings` → Create booking (protected)
- `GET /api/bookings/all` → Get all bookings (admin only)
- `POST /api/bookings/routes` → Create route (admin only)

---

## 👥 User Roles

### User
- Register & login
- Create bookings
- View personal bookings

### Admin
- Manage all bookings
- Create routes
- Access admin-only endpoints

---

## 🔐 Security

- Passwords hashed using bcrypt (10 rounds)
- JWT authentication with expiration
- Middleware-protected routes
- Role-based authorization system

---

## 📁 Project Structure

```
tapaRide/
│
└── backend/
    ├── config/
    ├── controllers/
    ├── middleware/
    ├── models/
    ├── routes/
    ├── .env.example
    ├── package.json
    └── server.js
```

---

## 🧪 Testing API

Use Postman or Thunder Client:

### Register
```
POST /api/auth/register

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "phone": "1234567890"
}
```

### Login
```
POST /api/auth/login

{
  "email": "john@example.com",
  "password": "password123"
}
```

Copy token and use:
```
Authorization: Bearer YOUR_TOKEN
```

---
## 📌 Notes

- Always run commands inside the `backend` folder
- Ensure MongoDB is running before starting server
- Keep `.env` file private (DO NOT push to GitHub)

