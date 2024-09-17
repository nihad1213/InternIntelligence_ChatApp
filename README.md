# Develop a Simple TCP/IP Chat Application.

# Task Description: 
Build a chat application that manages communication between a server and
multiple clients using TCP/IP sockets. The server should handle messages from clients and
broadcast them to other clients.

# Details: 
Develop both the server and client applications separately. Ensure the server can
handle multiple clients simultaneously. The client application should send messages to the
server and receive messages from other clients. Implement measures for reliability and error
handling.

# TCP/IP Chat Application Documentation

## Overview
The TCP/IP Chat Application allows multiple clients to connect to a server and communicate with each other in real-time. The server manages incoming connections and broadcasts messages sent by one client to all other connected clients.

## Features
- **Multi-client support**: Handle multiple client connections simultaneously.
- **Real-time messaging**: Broadcast messages from one client to all other clients.
- **Error handling**: Gracefully manage client disconnections and socket errors.

## Technologies Used
- **C++**: The primary programming language for developing the server and client applications.
- **TCP/IP Sockets**: Utilized for establishing communication between the server and clients.

## Components

### Server
- **File**: `server.cpp`
- **Responsibilities**:
  - Accept client connections.
  - Manage a list of connected clients.
  - Receive messages from clients and broadcast them to all other clients.
  - Handle client disconnections.

### Client
- **File**: `client.cpp`
- **Responsibilities**:
  - Connect to the server.
  - Send messages to the server.
  - Receive and display messages from other clients.

## Setup

### Prerequisites
- A C++ compiler (e.g., g++, clang++).
- Basic knowledge of terminal commands.

### Building the Application
1. **Compile the server and client code**:
   ```bash
   g++ server.cpp -o server -pthread
   g++ client.cpp -o client
   ```

2. **Run the server**:
   Open a terminal and execute:
   ```bash
   ./server
   ```

3. **Run the clients**:
   Open one or more additional terminal windows and execute:
   ```bash
   ./client
   ```

## Usage

1. After starting the server, each client will display the message:
   ```
   Connected to server. You can start chatting!
   ```

2. Clients can type messages and press Enter. For example:
   ```
   Hello everyone!
   ```

3. The server will broadcast the message to all other connected clients, displayed as:
   ```
   Client [socket_id]: Hello everyone!
   ```

4. Clients can disconnect by terminating the client program (using `Ctrl + C` or closing the terminal).

## Error Handling
- The server and client are designed to handle basic errors, such as connection issues and socket errors.
- If a client disconnects unexpectedly, the server logs the disconnection and continues to operate without affecting other clients.

## Conclusion
This TCP/IP Chat Application serves as a simple yet effective demonstration of real-time communication using C++ and TCP/IP sockets. It can be extended or modified to include additional features such as private messaging, user authentication, or a graphical user interface.