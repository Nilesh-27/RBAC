# RBAC Authentication System

A full-stack **Role-Based Access Control (RBAC)** system built with modern technologies to provide secure and scalable role-based authentication for Super Admin, Admin, and User roles.

---

## Features

- 🔐 **Role-Based Authentication**: Fine-grained access control for Super Admin, Admin, and User roles.
- 👥 **User Management Dashboard**: Manage user profiles, roles, and sessions.
- ⏰ **Session Timeout**: Automatic logout after 4 minutes of inactivity with activity reset functionality.
- 🔒 **Secure Password Handling**: Passwords hashed with Bcrypt for enhanced security.
- 📱 **Responsive Design**: Mobile-first, responsive layout for all devices.
- 🎨 **Modern UI/UX**: Intuitive and sleek interface built with Tailwind CSS.

---

## Technologies Used

### **Frontend**

- React 18 (with TypeScript)
- Tailwind CSS for styling
- Lucide React for icons
- Axios for API communication
- React Router DOM for navigation

### **Backend**

- Node.js and Express.js for server-side logic
- MongoDB for database management
- JWT for secure authentication
- Bcrypt.js for password hashing

---

## Installation and Setup

### **Prerequisites**

- Node.js (v14 or higher)
- MongoDB installed and running
- Git installed

### **Steps to Set Up**

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/rbac-auth-system.git
   cd rbac-auth-system
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Set up environment variables**:

   - Create a `.env` file in the root directory with the following:
     ```env
     MONGODB_URI=mongodb://localhost:27017/auth-system
     JWT_SECRET=your_jwt_secret_key
     PORT=5000
     ```

4. **Start the application**:

   ```bash
   # Start the backend server
   npm run server

   # Open a new terminal and start the frontend
   npm run dev
   ```

---

## API Endpoints

### **Authentication**

#### Register User

- **POST** `/api/auth/register`
  - **Request Body**:
    ```json
    {
      "username": "testuser",
      "email": "testuser@example.com",
      "password": "password123",
      "role": "user" | "admin" | "super_admin"
    }
    ```

## Login

- POST `/api/auth/login`
  - Request Body:
    ```json
    {
      "email": "testuser@example.com",
      "password": "password123"
    }
    ```

---

## User Management

## Get All Users (Admin/Super Admin only)

- GET `/api/users`
  - Headers:
    ```json
    {
      "Authorization": "Bearer <JWT_TOKEN>"
    }
    ```

## Delete User (Super Admin only)

- DELETE `/api/users/:userId`
  - Headers:
    ```json
    {
      "Authorization": "Bearer <JWT_TOKEN>"
    }
    ```

## Update Profile

- PUT `/api/users/profile`
  - Headers:
    ```json
    {
      "Authorization": "Bearer <JWT_TOKEN>"
    }
    ```
  - Request Body:
    ```json
    {
      "username": "updatedUsername",
      "password": "newPassword123" // optional
    }
    ```

---

## Password and Email Requirements

- Password:

  - Minimum 8 characters
  - At least one uppercase letter
  - At least one lowercase letter
  - At least one number
  - At least one special character (`#?!@$%^&*-`)

- Email:
  - Only Gmail addresses are accepted (`@gmail.com`).

---

## Role Permissions

## Super Admin

- View all users
- Delete users
- Manage admin accounts
- Update own profile

## Admin

- View all users
- Update own profile

## User

- Update own profile

---

## Session Management

- Automatic logout after 4 minutes of inactivity.
- Session reset on user activity.
- Secure JWT token storage for authentication.

---
