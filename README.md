# Activity Booking API

A simple REST API for a Basic Activity Booking App similar to MeetX.

## Repository

- GitHub: [https://github.com/RahulK847/activity-booking-app](https://github.com/RahulK847/activity-booking-app.git)

## Live Demo

- Render: _Coming soon!_ (Add your Render deployment URL here after deployment)

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

## Deployment Instructions (Render + MongoDB Atlas)

1. **Push your code to GitHub.**
2. **Create a free MongoDB Atlas cluster.**

   - Create a database user and whitelist your IP (or 0.0.0.0/0 for open access).
   - Get your connection string from Atlas. It looks like:
     ```
     mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/?retryWrites=true&w=majority
     ```
   - Add your database name after `.net/` and before `?`, e.g.:
     ```
     mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/activity-booking-app?retryWrites=true&w=majority
     ```
   - If your password contains special characters (like @), URL-encode them (e.g., `@` becomes `%40`).

3. **Deploy to Render:**

   - Go to [Render](https://render.com) and create a new Web Service.
   - Connect your GitHub repo.
   - Set build command: `npm install`
   - Set start command: `node index.js` or `npm start`
   - Add environment variables:
     - `PORT` (Render sets this automatically, but you can add it as 10000)
     - `MONGODB_URI` (your Atlas connection string with database name)
     - `JWT_SECRET` (your JWT secret key)
     - `JWT_EXPIRE` (e.g., 30d)
   - Deploy and wait for your Render URL (e.g., `https://your-app-name.onrender.com`)

4. **Test your API using Postman:**
   - Import the provided Postman collection.
   - Replace `http://localhost:5000` with your Render URL in all requests.

## API Testing

A Postman collection is included in the repository for testing all endpoints.

## License

MIT
