# Booking App - Backend Authentication & Authorization

Node.js/Express REST API with JWT authentication and role-based access control.

## Features

- Email/password authentication
- JWT token-based sessions
- Password hashing with bcrypt
- Role-based access control (User/Admin)
- Protected API endpoints
- Secure middleware for route protection

## Setup Instructions

1. Navigate to backend folder:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

5. Start the server:
```bash
npm run dev
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)
- `PUT /api/auth/updatepassword` - Update password (protected)

### Bookings
- `GET /api/bookings/my-bookings` - Get user's bookings (protected)
- `POST /api/bookings` - Create booking (protected)
- `GET /api/bookings/all` - Get all bookings (admin only)
- `POST /api/bookings/routes` - Create route (admin only)

## User Roles

- **User**: Can book tickets, make payments, view personal bookings
- **Admin**: Can manage routes, view all bookings, manage users

## Security Features

- Passwords hashed with bcrypt (10 salt rounds)
- JWT tokens for stateless authentication
- Protected routes with middleware
- Role-based authorization
- Token expiration (7 days default)


