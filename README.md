
# NodPad: Real-time Collaborative Notepad

NotiPad is a simple, real-time collaborative notepad built with Flutter for the frontend and Golang for the backend. Users can simultaneously edit the same document, and changes are instantly reflected across all connected clients via WebSocket communication.

## Features

- Real-time document editing across multiple clients
- WebSocket-based communication for fast updates
- User collaboration with visual indicators (cursor highlights, color-coded text)
- Built using Flutter for a cross-platform frontend (iOS, Android, Web)

## Architecture

This project consists of two main parts:

1. **Backend (Golang)**: A WebSocket server that handles connections, document state management, and broadcasting updates to clients.
2. **Frontend (Flutter)**: A mobile and web application that allows users to interact with the document in real time. It communicates with the backend via WebSocket.

## Prerequisites

Before getting started, make sure you have the following installed:

- [Flutter](https://flutter.dev/docs/get-started/install) (for frontend development)
- [Go](https://golang.org/dl/) (for backend development)

## Getting Started

Follow these steps to run both the server and client locally.

### 1. Backend (Golang)

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/notipad.git
   cd notipad/server
   ```

2. Install dependencies:
   ```bash
   go mod tidy
   ```

3. Run the WebSocket server:
   ```bash
   go run main.go
   ```
   The server will start on `ws://localhost:8080`.

### 2. Frontend (Flutter)

1. Clone the repository (if you haven’t already):
   ```bash
   git clone https://github.com/your-username/notipad.git
   cd notipad/frontend
   ```

2. Install Flutter dependencies:
   ```bash
   flutter pub get
   ```

3. Run the Flutter app:
   ```bash
   flutter run
   ```
   The app will start and connect to the WebSocket server at `ws://localhost:8080`.

### 3. Usage

Once both the backend and frontend are running, open the app on multiple devices or emulators. As you type in one instance, the document will update in real-time across all other instances.

### 4. Contributing

Contributions are welcome! If you’d like to contribute to the project, feel free to fork the repository, make changes, and submit a pull request.

## Project Structure

The project is divided into two main directories:

- **server/**: The Golang backend that handles WebSocket connections, document updates, and broadcasting.
  - **main.go**: The entry point of the Golang server.
  - **websocket.go**: Handles WebSocket communication.
  - **document.go**: Manages the document state.
  - **handlers/**: Contains handlers for WebSocket and HTTP requests.
  - **go.mod**: Go module configuration.

- **frontend/**: The Flutter frontend where users can edit the document in real time.
  - **main.dart**: The entry point for the Flutter app.
  - **websocket.dart**: Manages WebSocket communication in the frontend.
  - **document.dart**: Handles document editing logic and UI updates.
  - **screens/**: Contains Flutter screen layouts (e.g., `home.dart` for the main notepad view).

## Technologies Used

- **Golang**: Backend WebSocket server.
- **Flutter**: Cross-platform frontend development (iOS, Android, Web).
- **WebSocket**: Real-time communication between the server and the client.
- **TextField (Flutter)**: Used for editing the document in real-time.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.