# Realtime Chat — WebSocket Messaging

[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Next.js](https://img.shields.io/badge/Next.js_15-000000?logo=next.js)](https://nextjs.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_v4-38B2AC?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![WebSocket](https://img.shields.io/badge/WebSocket-010101?logo=socketdotio&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)

A real-time messaging application with room-based chat, connect/disconnect controls, and a clean modular monorepo architecture. Built from scratch using raw WebSocket protocol (`ws`) — no Socket.io abstraction.

**[Live Demo](https://realtime-chat-app-seven-eta.vercel.app/)**

---

## Why Raw WebSockets (Not Socket.io)

Most tutorials use Socket.io, which abstracts away the protocol. This project uses the raw `ws` library to understand what's actually happening:

| | Socket.io | Raw `ws` (this project) |
|---|-----------|-------------------------|
| Auto-reconnection | Built-in | Implemented manually |
| Room management | Built-in | Implemented manually |
| Fallback transport | Polling fallback | WebSocket only |
| Understanding | Abstracted | Full protocol control |

> Building with `ws` forced me to handle **connection lifecycle, room broadcasting, and error recovery** from scratch — the same problems you'd solve at scale.

## Architecture

```mermaid
graph TB
    subgraph Clients
        C1[Client A]
        C2[Client B]
        C3[Client C]
    end

    subgraph Backend["Backend (Render)"]
        WS[WebSocket Server<br/>Express + ws]
        RM[Room Manager]
        CM[Connection Map]
    end

    subgraph Frontend["Frontend (Vercel)"]
        UI[Next.js 15 UI]
        HC[WebSocket Hook]
    end

    C1 <-->|ws://| WS
    C2 <-->|ws://| WS
    C3 <-->|ws://| WS
    WS --> RM
    WS --> CM
    UI --> HC
    HC <-->|ws://| WS
```

```
realtime-chat-app/
├── backend-ws/              # WebSocket server
│   ├── src/index.ts         # Express + WS server, room logic, message broadcasting
│   ├── package.json
│   └── tsconfig.json
├── frontend-ws/             # Next.js client
│   ├── src/app/             # Pages and API routes
│   ├── src/components/      # Chat UI components
│   └── package.json
└── README.md
```

## Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| WS Server | Node.js, Express, `ws` library | Raw WebSocket control, no abstraction layer |
| Auth | JSON Web Tokens | Stateless authentication for WS connections |
| Frontend | Next.js 15, React, Tailwind v4 | SSR + client-side reactivity |
| Language | TypeScript | Type safety across both packages |
| Deploy | Render (backend) + Vercel (frontend) | Split-stack: WS server needs persistent process |

## Features

- **Room-based messaging** — Create and join topic-based chat rooms
- **Connect/disconnect controls** — Manual connection management from the UI
- **Real-time broadcasting** — Messages delivered instantly to all room members
- **Monorepo structure** — Backend and frontend in one repo with independent configs
- **TypeScript throughout** — Shared types between client and server

## Quick Start

```bash
# Clone
git clone https://github.com/siddgawad/realtime-chat-app.git
cd realtime-chat-app

# Backend
cd backend-ws
npm install
npm run build
npm run start          # Runs on ws://localhost:3003

# Frontend (new terminal)
cd frontend-ws
npm install
npm run dev            # Runs on http://localhost:3000
```

**Environment variables:**
```bash
# backend-ws/.env
PORT=3003

# frontend-ws/.env.local
NEXT_PUBLIC_WS_URL=ws://localhost:3003
```

## What This Demonstrates

- **WebSocket lifecycle** — Connection establishment, heartbeat, reconnection, graceful close
- **Room management** — Server-side room tracking, join/leave broadcasting
- **Message protocol** — Structured JSON messages with type discrimination
- **Monorepo discipline** — Separate packages with independent build configs
- **Split-stack deployment** — WS server on Render (persistent process), UI on Vercel (edge)

## License

MIT
