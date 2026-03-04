# Delivery Management Platform

A robust, real-time Delivery Management Platform built with the MERN stack. This application facilitates the complete lifecycle of delivery requests, featuring live tracking, automated notifications, and a comprehensive administrative dashboard.

## 🚀 Features

* **Real-time Communication**: Integrated with **Socket.io** to provide live updates and instant notifications throughout the delivery process.
* **Comprehensive Delivery Management**: Supports creating, accepting, and managing delivery requests with specialized status tracking.
* **Secure Authentication**: Implements **Passport.js** and JWT-based authentication, including Google OAuth integration.
* **Administrative Oversight**: Dedicated admin routes and dashboard for managing users and system-wide deliveries.
* **Automated Background Tasks**: Includes scheduled **Cron jobs** for reliable system operations.
* **File Handling**: Secure user profiles with support for image uploads via **Cloudinary**.

## 🛠️ Technical Stack

* **Frontend**: React 19, Vite, Redux Toolkit, Tailwind CSS 4.
* **Backend**: Node.js, Express.js.
* **Database**: MongoDB with Mongoose.
* **Real-time**: Socket.io.
* **Security**: Helmet, Express-rate-limit, and JWT.

## 📋 Prerequisites

* Node.js (v18 or higher)
* MongoDB (Local or Atlas)
* Cloudinary Account (for image uploads)
* SMTP credentials (for email services)
* Google OAuth (for signin with google)

## ⚙️ Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/aryanshukla21/delivery-app
    cd delivery-app
    ```

2.  **Server Setup:**
    ```bash
    cd server
    npm install
    ```
    Create a `.env` file in the `server` directory:
    ```env
    NODE_ENV=development
    PORT=5000
    CLIENT_URL=http://localhost:3000
    MONGODB_URI=<your own database url>
    MONGODB_PASS=<your own pass>

    JWT_SECRET=<your own jwt secret>
    JWT_EXPIRE=7d
    JWT_REFRESH_SECRET=<your own refresh code>
    JWT_REFRESH_EXPIRE=30d

    GOOGLE_CLIENT_ID=<your own google client id>
    GOOGLE_CLIENT_SECRET=<your own google client secret>
    GOOGLE_CALLBACK_URL=<your own callback url>

    CLOUDINARY_NAME= <your_cloudinary_name>
    CLOUDINARY_API_KEY= <your_api_key>
    CLOUDINARY_API_SECRET= <your_api_secret>

    RAZORPAY_KEY_ID = <your razorpay key id>
    RAZORPAY_KEY_SECRET = <your own razorpay secret>

    SMTP_HOST=smtp.gmail.com
    SMTP_PORT=587
    SMTP_USER=<your won email>
    SMTP_PASS=<your won pass>

    ENCRYPTION_SECRET=<your own encryption secret>
    ```

3.  **Client Setup:**
    ```bash
    cd ../client
    npm install
    ```
    Create a `.env` file in the `client` directory:
    ```env
    VITE_API_URL=http://localhost:5000/api
    VITE_SOCKET_URL=http://localhost:5000
    VITE_RAZORPAY_KEY_ID=rzp_test_your_key_id
    ```

## 🚀 Running the Application

1.  **Start the Backend:**
    ```bash
    cd server
    npm run dev
    ```

2.  **Start the Frontend:**
    ```bash
    cd client
    npm run dev
    ```

## 📂 Project Structure

* `/client`: React frontend with Vite and Redux Toolkit.
* `/server/src/models`: Mongoose schemas (User, Delivery, Notification, Payment).
* `/server/src/config`: Logic for configuration files (Cludinary, db, Passport, Payment, Socket).
* `/server/src/controllers`: Logic for handling API requests.
* `/server/src/middlewares`: Logic for middlewares like (Auth, Error, rateLimiter, role, upload, validation).
* `/server/src/routes`: Contains all the API routes files.
* `/server/src/socket`: Socket.io event handlers for real-time features.
* `/server/src/services`: Core services for Email, Payments, and Cron jobs.