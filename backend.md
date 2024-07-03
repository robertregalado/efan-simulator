
# Node.js Server Documentation

## Table of Contents

1. **Overview**
2. **Dependencies**
3. **Server Setup**
4. **Socket.IO Integration**
5. **Static File Serving**
6. **Event Handling**
7. **Error Handling**
8. **Usage**

---

### 1. Overview

Welcome to the documentation for the Node.js server code that implements a fan speed control system using Express and Socket.IO. This server facilitates real-time communication between clients (frontend) and the server to control and monitor the fan simulation.

### 2. Dependencies

- **Express:** Fast, unopinionated, minimalist web framework for Node.js.
- **http:** Core Node.js module for creating HTTP servers.
- **Socket.IO:** Real-time bidirectional event-based communication library for web applications.

### 3. Server Setup

The server is initialized and configured as follows:

```javascript
const express = require('express');
const http = require('http');
const socketIo = require('socket.io');

const app = express();
const server = http.createServer(app);
const io = socketIo(server);
```

- **`express()`:** Creates an Express application instance (`app`).
- **`http.createServer(app)`:** Creates an HTTP server instance (`server`) using the Express application.
- **`socketIo(server)`:** Integrates Socket.IO with the HTTP server to enable real-time communication.

### 4. Socket.IO Integration

Socket.IO is used to manage client-server communication:

```javascript
io.on('connection', (socket) => {
    console.log('a user connected');

    socket.on('setSpeed', (speed) => {
        console.log(`Fan speed set to: ${speed}`);
        io.emit('updateSpeed', speed);
    });

    socket.on('disconnect', () => {
        console.log('user disconnected');
    });
});
```

- **`io.on('connection', (socket) => { ... })`:** Listens for incoming socket connections from clients.
  - **`socket.on('setSpeed', (speed) => { ... })`:** Listens for the `setSpeed` event from clients to set the fan speed and emits the `updateSpeed` event to all connected clients.
  - **`socket.on('disconnect', () => { ... })`:** Listens for disconnection events and logs when a client disconnects.

### 5. Static File Serving

Static files (e.g., HTML, CSS, client-side JavaScript) are served from the `public` directory:

```javascript
app.use(express.static('public'));
```

- **`express.static('public')`:** Middleware that serves static files located in the `public` directory.

### 6. Event Handling

- **`socket.on('setSpeed', ...)`:** Handles client requests to set the fan speed.
- **`socket.on('disconnect', ...)`:** Handles client disconnections.

### 7. Error Handling

Error handling is not explicitly included in this code snippet but can be added using Express middleware or Socket.IO error events for robust error management.

### 8. Usage

To use the Node.js server:

- Save the code to a file (e.g., `server.js`).
- Install dependencies (`express`, `http`, `socket.io`) using npm (`npm install express http socket.io`).
- Run the server using Node.js (`node server.js`).
- Ensure the frontend (HTML, CSS, client-side JavaScript) interacts correctly with the server for fan speed control.

