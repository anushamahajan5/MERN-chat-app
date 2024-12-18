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

# Scalability
Efficient Backend Architecture:
## Database Design: 
Implemented MongoDB with a schema optimized for real-time chat data. Indexed frequently queried fields like userId and chatId for faster data retrieval.
Schema Optimization:

I designed MongoDB collections to store data in a structured and efficient way:
User Collection: Stores user details like userId, username, and status.
Chat Collection: Stores chatId, participants, and a reference to the messages.
Message Collection: Stores messageId, chatId, senderId, content, and timestamp.
By separating data into collections and referencing related items, the database avoids duplication and remains easy to manage.

Indexing:
Indexed frequently queried fields like userId and chatId using MongoDB’s built-in indexing feature. For example:
```javascript
db.messages.createIndex({ chatId: 1, timestamp: -1 });
```

## Horizontal Scaling: 
Designed the backend with stateless REST APIs using Express to allow horizontal scaling by deploying multiple instances of the app behind a load balancer.
tateless REST APIs:

The backend was built with Express.js and designed so each request is independent (stateless). For instance:
Each API call, like fetching messages or sending one, includes all necessary information (e.g., user ID and authentication token).
This made it easy to deploy multiple backend instances.

Load Balancer Setup(*TODO*):
Deployed the backend on multiple instances using Docker and ran them behind a load balancer (e.g., NGINX or AWS ELB).
The load balancer distributes incoming requests across the instances, ensuring no single instance gets overwhelmed.

## Socket.IO Integration: Used Socket.IO for real-time communication with efficient message broadcasting mechanisms, reducing overhead for clients and server.

## Rate Limiting: Implemented rate-limiting middleware to handle bursts of user requests without overloading the system.

**Middleware Implementation:**
Used express-rate-limit middleware to restrict the number of API requests a user or IP can make in a specific time. For example:

```javascript
const rateLimit = require("express-rate-limit");

const apiLimiter = rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100, // Limit each IP to 100 requests per windowMs
});

app.use("/api/", apiLimiter);
```

Benefits:
1. Protected the system from overload during traffic spikes or intentional abuse.
2. Ensured a smooth experience for all users by distributing resources fairly.

---

This project demonstrates the power of the MERN stack in building modern, scalable, and real-time applications.
