# Code-Sync: Real-Time Collaborative Code Editor

Code-Sync is a web-based, real-time collaborative code editor that allows multiple users to code, chat, and draw together in a shared workspace. It's built with React, Node.js, and WebSockets, providing a seamless and interactive experience for remote pair programming, interviews, and teaching.

## ✨ Features

-   **Real-Time Collaboration**: See changes from other users instantly, including code, cursor positions, and selections.
-   **Rich Code Editor**: A powerful editor based on CodeMirror with syntax highlighting for numerous languages.
-   **File & Directory Management**: Create, rename, and delete files and folders, all synced in real time.
-   **Integrated Chat**: Communicate with other users in the room without leaving the editor.
-   **User Presence**: See who is currently online, offline, or typing.
-   **Code Execution**: Run code snippets directly in the editor using the Piston API.
-   **Collaborative Whiteboard**: Shared drawing canvas for brainstorming and diagrams.
-   **Customizable Themes**: Multiple light and dark themes.
-   **Room-Based Sessions**: Create unique rooms for private collaboration.

## 🛠️ Tech Stack

### Frontend

-   React & TypeScript
-   Vite
-   Tailwind CSS
-   Socket.IO Client
-   CodeMirror 6

### Backend

-   Node.js & Express
-   TypeScript
-   Socket.IO

### Deployment

-   Docker & Docker Compose

## 🚀 Getting Started

### Prerequisites

-   Node.js (v18 or later)
-   npm or yarn
-   Docker & Docker Compose

### 🧑‍💻 Local Development

1.  **Clone the repository**

    ```bash
    git clone https://github.com/Vishwa-Bhalodiya/Code-sync.git
    cd Code-sync
    ```

2.  **Backend Setup**

    ```bash
    cd server
    npm install
    ```

    Create a `.env` file inside the `server` folder:

    ```
    PORT=3000
    ```

    Start the backend:

    ```bash
    npm run dev
    ```

3.  **Frontend Setup**

    ```bash
    cd ../client
    npm install
    npm run dev
    ```

4.  **Access the App**
    -   **Frontend**: `http://localhost:5173`
    -   **Backend**: `http://localhost:3000`

### 🐳 Docker Deployment (Recommended)

The project is fully configured using Docker Compose.

1.  **Build the containers**

    ```bash
    docker compose build
    ```

2.  **Start the application**

    ```bash
    docker compose up
    ```

3.  **Access the App**

    Open your browser and go to:

    `http://localhost:5173`

    To run in detached mode:

    ```bash
    docker compose up -d
    ```

    To stop the containers:

    ```bash
    docker compose down
    ```

## 📁 Project Structure

```
.
├── client/         # React frontend
│   ├── src/
│   ├── Dockerfile
│   └── package.json
├── server/         # Node.js backend
│   ├── src/
│   ├── Dockerfile
│   └── package.json
└── docker-compose.yml
```

## 🔌 Socket API Events

### Connection

-   `JOIN_REQUEST`
-   `JOIN_ACCEPTED`
-   `USER_JOINED`
-   `USER_DISCONNECTED`

### File System

-   `SYNC_FILE_STRUCTURE`
-   `FILE_CREATED`
-   `FILE_DELETED`
-   `FILE_RENAMED`

### Editor

-   `TYPING_START`
-   `TYPING_PAUSE`
-   `CURSOR_MOVE`
-   `FILE_UPDATED`

### Chat

-   `SEND_MESSAGE`
-   `RECEIVE_MESSAGE`

### Drawing

-   `DRAWING_UPDATE`
-   `SYNC_DRAWING`
