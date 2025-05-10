# Activity Booking API

A simple REST API for a Basic Activity Booking App similar to MeetX.

## Features

- User Registration & Login (JWT Authentication)
- List Activities (Public)
- Book Activities (Authenticated Users Only)
- View User's Bookings

## Tech Stack

- Node.js with Express.js
- MongoDB with Mongoose
- JWT for Authentication
- Express Validator for Input Validation
- Bcrypt for Password Hashing

## API Endpoints

### Users

- **Register User**: `POST /api/users/register`
  - Body: `{ name, email, phone, password }`
- **Login User**: `POST /api/users/login`
  - Body: `{ email, password }`
  - Returns: JWT token

### Activities

- **Get All Activities**: `GET /api/activities`
  - Public endpoint
- **Get Single Activity**: `GET /api/activities/:id`
  - Public endpoint
- **Create Activity**: `POST /api/activities`
  - Protected endpoint
  - Body: `{ title, description, location, dateTime }`

### Bookings

- **Book an Activity**: `POST /api/bookings`
  - Protected endpoint
  - Body: `{ activityId }`
- **Get My Bookings**: `GET /api/bookings/me`
  - Protected endpoint

## Setup Instructions

1. Clone the repository

```
git clone <repository-url>
```

2. Install dependencies

```
npm install
```

3. Create a `.env` file in the root directory with the following variables:

```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/activity-booking-app
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRE=30d
```

4. Start the server

```
npm run dev
```

## API Testing

A Postman collection is included in the repository for testing all endpoints.

## Deployment

You can deploy this API to platforms like Render, Vercel, or Cyclic.

## License

MIT
