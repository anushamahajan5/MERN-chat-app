# MERN-chat-app

This is a chat application built using the MERN stack (MongoDB, Express.js, React, and Node.js).

---

## Explanation

### **Frontend**
The frontend was developed using **React** with the following libraries:
- **Axios**: For handling API requests.
- **React Router**: To enable seamless navigation between pages.
- **Material-UI (MUI)**: For responsive and visually appealing components.

The frontend consists of the following web pages:
- **Login Page**: Allows users to securely log in to their accounts.
- **Chat Page**: Enables real-time messaging between users.

### **Backend**
The backend is built with **Node.js** and **Express.js**, with the main API file named `index.js`. The following libraries are used:
- **Express**: For setting up the server and defining RESTful API endpoints.
- **Mongoose**: To connect and interact with the MongoDB database.
- **bcrypt.js**: For securely hashing user passwords.
- **jsonwebtoken (JWT)**: For user authentication and authorization.
- **Socket.IO**: To enable real-time chat functionality.

---

## Use of Each Library

1. **React Router**: Handles routing between the Login and Chat pages.
2. **Axios**: Manages HTTP requests to interact with backend APIs.
3. **Material-UI**: Provides reusable UI components for designing the interface.
4. **Express**: Handles API routing and middleware integration on the backend.
5. **Mongoose**: Facilitates schema definition and database operations.
6. **Socket.IO**: Supports real-time communication for sending and receiving messages instantly.

---

## Screenshots

### Login Page
The login page allows users to authenticate themselves with their credentials.  
![Login Page](https://github.com/anushamahajan5/MERN-chat-app/assets/99132058/e5b7674e-3c54-4094-a437-3e7f06c41072)

---

### Chat Page
This is the main interface for chatting, where users can send and receive messages in real time.  
![Chat Page](https://github.com/anushamahajan5/MERN-chat-app/assets/99132058/f9f5b7cf-9874-4970-81ed-49dace6e7840)

---

### MongoDB Database
The MongoDB database stores user information, chat messages, and other related data.  
![MongoDB Database](https://github.com/anushamahajan5/MERN-chat-app/assets/99132058/82bc2849-30bd-4e16-afda-8a298fe16beb)

---

## Features
- Real-time chat using **Socket.IO**.
- Secure user authentication with **bcrypt.js** and **JWT**.
- Responsive and user-friendly UI designed with **Material-UI**.
- Scalable backend architecture supporting multiple users simultaneously.

---

This project demonstrates the power of the MERN stack in building modern, scalable, and real-time applications.
