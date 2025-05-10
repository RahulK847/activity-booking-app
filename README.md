# 🌟 **Activity Booking API**

A simple REST API for a basic activity booking app.

---

## 📂 Repository

- **GitHub**: [https://github.com/RahulK847/activity-booking-app](https://github.com/RahulK847/activity-booking-app.git)

## 🚀 Live Demo

- **Render**: [https://activity-booking-app-0b52.onrender.com](https://activity-booking-app-0b52.onrender.com)

---

## ✨ Features

✅ User Registration & Login (JWT Authentication)  
✅ List Activities (Public)  
✅ Book Activities (Authenticated Users Only)  
✅ View User’s Bookings

---

## 🛠 Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB (Atlas), Mongoose
- **Auth**: JWT (JSON Web Tokens)
- **Security**: Bcrypt for password hashing
- **Validation**: Express Validator

---

## 📌 API Endpoints

### 🔑 Users

- **Register User**  
  `POST /api/users/register`  
  **Body:**

  ```json
  {
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "1234567890",
    "password": "your_password"
  }
  ```

- **Login User**  
  `POST /api/users/login`  
  **Body:**
  ```json
  {
    "email": "john@example.com",
    "password": "your_password"
  }
  ```
  **Returns:** JWT token

---

### 🎯 Activities

- **Get All Activities** (Public)  
  `GET /api/activities`

- **Get Single Activity** (Public)  
  `GET /api/activities/:id`

- **Create Activity** (Protected)  
  `POST /api/activities`  
  **Body:**
  ```json
  {
    "title": "Yoga Class",
    "description": "Morning yoga session",
    "location": "Community Center",
    "dateTime": "2025-06-01T08:00:00Z"
  }
  ```

---

### 📅 Bookings

- **Book an Activity** (Protected)  
  `POST /api/bookings`  
  **Body:**

  ```json
  {
    "activityId": "activity_object_id"
  }
  ```

- **Get My Bookings** (Protected)  
  `GET /api/bookings/me`

---

## ⚙️ Setup Instructions (Local)

1️⃣ **Clone the repository and install dependencies:**

```bash
git clone https://github.com/RahulK847/activity-booking-app.git
cd activity-booking-app
npm install
```

2️⃣ **Create a `.env` file in the root directory:**

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/activity-booking-app
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRE=30d
```

3️⃣ **Start the server:**

```bash
npm run dev
```

---

## 🔍 API Testing

✅ **Postman Collection** included in the repository.

- Import `activity-booking-api.postman_collection.json` into Postman.

🔗 **Example Endpoints:**  
| Action | URL |
|-------------------------|-----------------------------------------------------------------|
| Register User | `https://activity-booking-app-0b52.onrender.com/api/users/register` |
| Login User | `https://activity-booking-app-0b52.onrender.com/api/users/login` |
| Get All Activities | `https://activity-booking-app-0b52.onrender.com/api/activities` |
| Get Single Activity | `https://activity-booking-app-0b52.onrender.com/api/activities/:id` |
| Create Activity | `https://activity-booking-app-0b52.onrender.com/api/activities` |
| Book an Activity | `https://activity-booking-app-0b52.onrender.com/api/bookings` |
| Get My Bookings | `https://activity-booking-app-0b52.onrender.com/api/bookings/me` |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
