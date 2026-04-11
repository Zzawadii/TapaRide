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

3. Create `.env` file:
```bash
copy .env.example .env
```

4. Update `.env` with your MongoDB URI and JWT secret

5. Start the server:
```bash
npm run dev
```

Backend API will run on http://localhost:5000

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

## Testing with Postman or Thunder Client

### 1. Register a new user
- Method: POST
- URL: `http://localhost:5000/api/auth/register`
- Body (JSON):
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "phone": "1234567890"
}
```

### 2. Login
- Method: POST
- URL: `http://localhost:5000/api/auth/login`
- Body (JSON):
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```
- Response will include a JWT token - copy this token

### 3. Access protected route
- Method: GET
- URL: `http://localhost:5000/api/auth/me`
- Headers:
  - Key: `Authorization`
  - Value: `Bearer YOUR_JWT_TOKEN`

### 4. Test admin route
- Method: GET
- URL: `http://localhost:5000/api/bookings/all`
- Headers:
  - Key: `Authorization`
  - Value: `Bearer YOUR_JWT_TOKEN`
- Note: This will only work if the user has admin role
