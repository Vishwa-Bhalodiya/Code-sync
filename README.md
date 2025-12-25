# Code-Sync: Real-Time Collaborative Code Editor

Code-Sync is a web-based, real-time collaborative code editor that allows multiple users to code, chat, and draw together in a shared workspace. It's built with React, Node.js, and WebSockets, providing a seamless and interactive experience for remote pair programming, interviews, and teaching..

## ✨ Features

-   **Real-Time Collaboration**: See changes from other users instantly, including code, cursor positions, and selections.
-   **Rich Code Editor**: A powerful editor based on CodeMirror with syntax highlighting for numerous languages.
-   **File & Directory Management**: A complete file explorer where you can create, rename, and delete files and folders, all synced in real-time.
-   **Integrated Chat**: Communicate with other users in the room without leaving the editor.
-   **User Presence**: See who is currently online, offline, or typing in the room.
-   **Code Execution**: Run code snippets directly in the editor using the Piston API.
-   **Collaborative Whiteboard**: A shared drawing canvas for brainstorming and diagramming.
-   **Customizable Themes**: Switch between multiple light and dark themes for the editor and UI.
-   **Room-Based Sessions**: Create unique rooms for private, collaborative sessions.

## 🛠️ Tech Stack

-   **Frontend**:
    -   React & TypeScript
    -   Vite
    -   Tailwind CSS
    -   Socket.IO Client
    -   CodeMirror 6
-   **Backend**:
    -   Node.js & Express
    -   TypeScript
    -   Socket.IO
-   **Deployment**:
    -   Docker

## 🚀 Getting Started

Follow these instructions to get a local copy up and running for development and testing purposes.

### Prerequisites

-   [Node.js](https://nodejs.org/) (v18 or later recommended)
-   [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
-   [Docker](https://www.docker.com/products/docker-desktop/) (for containerized deployment)

### Local Development

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/your-username/Code-Sync.git
    cd Code-Sync
    ```

2.  **Set up the Backend:**
    ```sh
    cd server
    npm install
    ```
    Create a `.env` file in the `server` directory and add the port:
    ```env
    # .env
    PORT=3000
    ```
    Start the backend server:
    ```sh
    npm run dev
    ```

3.  **Set up the Frontend:**
    ```sh
    cd ../client
    npm install
    ```
    Start the frontend development server:
    ```sh
    npm run dev
    ```

4.  **Access the application:**
    Open your browser and navigate to `http://localhost:5173`. The backend will be running on `http://localhost:3000`.

## 🐳 Docker Deployment

The project is fully configured for containerization.

1.  **Build the Docker images:**

    Build the server image:
    ```sh
    # From the /server directory
    docker build -t your-docker-username/code-sync-server:latest .
    ```

    Build the client image:
    ```sh
    # From the /client directory
    docker build -t your-docker-username/code-sync-client:latest .
    ```

2.  **Run the Docker containers:**

    Start the server container:
    ```sh
    docker run -d -p 3000:3000 --name code-sync-server your-docker-username/code-sync-server:latest
    ```

    Start the client container, linking it to the server:
    ```sh
    docker run -d -p 5173:5173 -e VITE_BACKEND_URL=http://localhost:3000 --name code-sync-client your-docker-username/code-sync-client:latest
    ```

3.  **Access the application:**
    Open your browser and navigate to `http://localhost:5173`.

## 📁 Project Structure

The repository is organized into two main parts: a `client` folder and a `server` folder.

```
.
├── client/         # Contains the React frontend application
│   ├── src/
│   ├── Dockerfile
│   └── package.json
└── server/         # Contains the Node.js/Express backend
    ├── src/
    ├── Dockerfile
    └── package.json
```

## 🔌 Socket API

Communication between the client and server is handled via WebSockets using Socket.IO. Here are some of the key events:

-   **Connection**: `JOIN_REQUEST`, `JOIN_ACCEPTED`, `USER_JOINED`, `USER_DISCONNECTED`
-   **File System**: `SYNC_FILE_STRUCTURE`, `FILE_CREATED`, `FILE_DELETED`, `FILE_RENAMED`
-   **Editor**: `TYPING_START`, `TYPING_PAUSE`, `CURSOR_MOVE`, `FILE_UPDATED`
-   **Chat**: `SEND_MESSAGE`, `RECEIVE_MESSAGE`
-   **Drawing**: `DRAWING_UPDATE`, `SYNC_DRAWING`

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improving the app, please feel free to open an issue or submit a pull request.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📄 License

This project is distributed under the MIT License. See `LICENSE` for more information.
