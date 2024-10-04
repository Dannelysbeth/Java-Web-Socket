# Simple Chat Application

This is a simple chat application built with Spring Boot, WebSockets, and STOMP for real-time messaging. It includes a frontend that allows users to connect, send messages, and receive greetings.

## Features

- Real-time messaging using WebSocket and STOMP protocol
- Frontend built with HTML, JavaScript, and jQuery
- WebSocket communication handled using SockJS and Stomp.js
- Lightweight Spring Boot backend with STOMP message broker

## Project Structure

- **Backend**:
  - `ChatController.java`: Handles incoming chat messages and broadcasts them to all clients subscribed to `/topic/messages`.
  - `ChatWebSocketHandler.java`: Custom WebSocket handler managing WebSocket connections and broadcasting messages.
  - `WebSocketConfig.java`: Configures WebSocket and STOMP message broker.
  - `HelloMessage.java` & `Greetings.java`: Models for handling incoming and outgoing message formats.
  - `SimpleChatApplication.java`: Main class to run the Spring Boot application.

- **Frontend**:
  - `index.html`: Web interface for connecting to WebSocket, sending a name, and displaying greetings.
  - `app.js`: JavaScript handling WebSocket connection, sending messages, and receiving responses.
  - `main.css`: Basic styling for the web interface.

## Requirements

- Java 17 or higher (set to use Java 23 toolchain)
- Gradle 7.0+
- Spring Boot 3.3.4
- SockJS and Stomp.js for WebSocket communication

## How to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/simple-chat.git
    cd simple-chat
    ```

2. Build and run the application using Gradle:
    ```bash
    ./gradlew bootRun
    ```

3. Open your browser and navigate to `http://localhost:8080` to use the chat application.

## WebSocket Endpoints

- **/stomp-endpoint**: WebSocket endpoint that clients connect to via SockJS.
- **/topic/greetings**: Destination for receiving broadcasted greetings.
- **/app/hello**: Endpoint to send the user's name.

## Static Files

- **app.js**: Manages WebSocket connections using Stomp.js, sending messages, and displaying received greetings.
- **index.html**: Frontend interface with input fields for connecting and sending names.
- **main.css**: Simple CSS for basic styling.

## Example WebSocket Message

To send a name from the client:
```json
{
    "name": "Alice"
}
```



