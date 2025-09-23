# 🔌 WebSocket Chat Server

A lightweight **TypeScript + ws** WebSocket server that powers realtime chat rooms.  
Currently deployed and running live 🚀  

## ✨ Features
- Multiple chat rooms (join/leave anytime)  
- Broadcast messages to everyone in the room  
- Type-safe message parsing (`join`, `chat`)  
- Cleanup on disconnect  
- Simple HTTP health check (`/ → ok`)  

## 🛠️ Tech Stack
- Node.js + TypeScript  
- [ws](https://github.com/websockets/ws) WebSocket library  
- HTTP server for health checks  

## 🚀 Getting Started

### Prerequisites
- Node.js 18+  
- npm  

### Setup
```bash
# clone the repo
git clone https://github.com/siddgawad/websockets-backend.git
cd websockets-backend

# install deps
npm install

# build
npm run build

# start server
node dist/index.js
