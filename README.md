# Ride Booking System (RideShare)

A full-stack ride booking and ride-sharing platform built with the MERN stack as a final year project. It supports three roles (Passenger, Rider and Admin) with real-time chat, live ride tracking, emergency SOS alerts and a complete admin panel.

## Features

### Passenger
- Sign up, login, forgot/reset password and profile completion
- Find rides, book rides and manage bookings
- Live ride tracking on a map
- Ride history and nearby area riders
- Real-time chat with riders
- Emergency SOS alerts
- Submit complaints
- In-app notifications

### Rider
- Rider profile and vehicle registration (add, edit, manage vehicles)
- Offer rides and manage posted rides
- Chat with passengers
- Rider dashboard

### Admin
- User approvals and verification portal
- User directory and registration number directory
- Complaint management
- System analytics dashboard
- Admin management with audit logs
- System settings

### General
- Role-based access control with protected routes
- Real-time updates using Socket.io
- Email and SMS notifications
- Image uploads with ImageKit
- Reverse geocoding for location names
- Progressive Web App (PWA) support
- Admin and registration-number seeding scripts

## Tech Stack

| Layer | Technologies |
|-------|--------------|
| Frontend | React (Vite), Redux Toolkit, React Router, Axios |
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose |
| Real-time | Socket.io |
| Authentication | JWT, bcrypt |
| Services | ImageKit, Email (Nodemailer), SMS |

## Project Structure

```
fyp-main/
├── client/                 # React frontend
│   └── src/
│       ├── components/     # Reusable UI, layout, maps, auth
│       ├── pages/          # admin, passenger, rider pages
│       ├── store/          # Redux slices
│       └── utils/          # API, socket, upload helpers
└── server/                 # Express backend
    ├── config/             # Database connection
    ├── controllers/        # Business logic
    ├── middleware/         # Auth middleware
    ├── models/             # Mongoose schemas
    ├── routes/             # API routes
    ├── services/           # SMS service
    └── utils/              # Email, geocoding, seed scripts
```

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- MongoDB (local or MongoDB Atlas)

### 1. Clone the repository
```bash
git clone https://github.com/qiratrasheed/ride-booking-system-mern.git
cd ride-booking-system-mern/fyp-main
```

### 2. Backend setup
```bash
cd server
npm install
```
Create a `.env` file in `server/` with your own values (never commit this file):
```
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
EMAIL_USER=your_email
EMAIL_PASS=your_email_app_password
```
Add any other keys used by the SMS and ImageKit services.

Seed the admin account and registration numbers (optional):
```bash
node utils/seedAdmin.js
node utils/seedRegistrationNumbers.js
```
Start the server:
```bash
npm start
```

### 3. Frontend setup
```bash
cd client
npm install
cp .env.example .env
npm run dev
```
Fill in the values in `client/.env` (API URL, ImageKit keys, etc.).

The app runs at `http://localhost:5173` and the API at `http://localhost:5000`.

## License
This project is for educational purposes.
