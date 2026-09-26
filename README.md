# Online Code Editor

A collaborative online code editor built with **React + Monaco Editor** on the frontend and **Express + Socket.IO + Yjs** on the backend.

## Features

- Real-time collaborative editing
- Shared awareness with active user list
- Monaco editor with JavaScript default language
- Backend health check endpoint (`/health`)
- Docker support for full-stack deployment

## Tech Stack

### Frontend
- React (Vite)
- Monaco Editor (`@monaco-editor/react`)
- Yjs + y-monaco + y-socket.io
- Tailwind CSS

### Backend
- Node.js
- Express
- Socket.IO
- Yjs + y-socket.io server

## Project Structure

- `/Frontend` — React client application
- `/Backend` — Express + Socket.IO server
- `/dockerfile` — Multi-stage Docker build (frontend build + backend runtime)

## Getting Started

### Prerequisites

- Node.js 20+
- npm

### 1) Install dependencies

```bash
cd /home/runner/work/Online-Code-Editor/Online-Code-Editor/Frontend && npm install
cd /home/runner/work/Online-Code-Editor/Online-Code-Editor/Backend && npm install
```

### 2) Run frontend (development UI)

```bash
cd /home/runner/work/Online-Code-Editor/Online-Code-Editor/Frontend
npm run dev
```

### 3) Run backend

```bash
cd /home/runner/work/Online-Code-Editor/Online-Code-Editor/Backend
npm run dev
```

Backend runs on `http://localhost:8080`.

## Docker Run

Build and run the app:

```bash
cd /home/runner/work/Online-Code-Editor/Online-Code-Editor
docker build -t online-code-editor -f dockerfile .
docker run -p 8080:8080 online-code-editor
```

Then open `http://localhost:8080`.

## Available Scripts

### Frontend (`/Frontend`)
- `npm run dev` — Start Vite dev server
- `npm run build` — Build production assets
- `npm run lint` — Run ESLint
- `npm run preview` — Preview built frontend

### Backend (`/Backend`)
- `npm run dev` — Start server with nodemon
- `npm run start` — Start server with Node

## Health Check

```bash
curl http://localhost:8080/health
```

Expected response:

```json
{
  "message": "ok",
  "success": true
}
```

## License

MIT — see [LICENSE](LICENSE).
