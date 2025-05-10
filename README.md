# Activity Booking API

A simple REST API for a Basic Activity Booking App similar to MeetX.

## Repository

- GitHub: [https://github.com/RahulK847/activity-booking-app](https://github.com/RahulK847/activity-booking-app.git)

## Live Demo

- Render: [https://activity-booking-app-0b52.onrender.com](https://activity-booking-app-0b52.onrender.com)

## Features

- User Registration & Login (JWT Authentication)
- List Activities (Public)
- Book Activities (Authenticated Users Only)
- View User's Bookings

## Tech Stack

- Node.js with Express.js
- MongoDB with Mongoose (Atlas for cloud hosting)
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

## Setup Instructions (Local)

1. Clone the repository and install dependencies:
   ```
   git clone https://github.com/RahulK847/activity-booking-app.git
   cd activity-booking-app
   npm install
   ```
2. Create a `.env` file in the root directory:
   ```
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/activity-booking-app
   JWT_SECRET=your_jwt_secret_key_here
   JWT_EXPIRE=30d
   ```
3. Start the server:

   ```
   npm run dev
   ```

4. **Test your API using Postman:**
   - Import the provided Postman collection.
   - Replace `http://localhost:5000` with your Render URL in all requests.

## API Testing

A Postman collection is included in the repository for testing all endpoints.

```
Import activity-booking-api.postman_collection.json into your Postman for API Testing
```

## License

MIT
