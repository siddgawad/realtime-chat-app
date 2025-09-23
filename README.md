# 💬 Realtime Chat App (WebSockets)

A **full-stack realtime chat application** built with:
- **Backend** → Node.js, Express, TypeScript, WebSocket (`ws`)  
- **Frontend** → Next.js 15, TypeScript, TailwindCSS  

🌐 Live demo: [Backend](https://your-backend.onrender.com) | [Frontend](https://your-frontend.vercel.app)

---

## ✨ Features
- 🔌 WebSocket server with room-based messaging  
- ⚡ Connect/disconnect from client  
- 💬 Join chat rooms & broadcast messages  
- 🎨 Modern UI with TailwindCSS  
- 📦 Modular monorepo structure (backend-ws & frontend-ws)  

---

## 📂 Project Structure
realtime-chat-app/
│
├── backend-ws/ # WebSocket backend (Express + WS)
│ ├── src/...
│ ├── package.json
│ └── tsconfig.json
│
├── frontend-ws/ # Next.js frontend (React + Tailwind)
│ ├── src/app/...
│ ├── package.json
│ └── tsconfig.json
│
└── README.md # You are here 🚀

yaml
Copy code

---

## 🛠️ Tech Stack
- **Backend**: Node.js, Express, TypeScript, WebSocket (`ws`)  
- **Frontend**: Next.js 15, TailwindCSS v4, TypeScript  
- **Deployment**: Render (backend), Vercel (frontend)  

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/siddgawad/realtime-chat-app.git
cd realtime-chat-app
2. Backend setup
bash
Copy code
cd backend-ws
npm install
npm run dev
Backend runs on: http://localhost:3003 (HTTP) and ws://localhost:3003 (WebSocket)

3. Frontend setup
bash
Copy code
cd frontend-ws
npm install
npm run dev
Frontend runs on: http://localhost:3000

4. Environment Variables
Backend (backend-ws/.env)
ini
Copy code
PORT=3003
Frontend (frontend-ws/.env.local)
ini
Copy code
NEXT_PUBLIC_WS_URL=ws://localhost:3003
📌 Usage
Start the backend.

Start the frontend.

Open the frontend in multiple tabs.

Connect → Join a room → Send messages → See realtime chat 🚀

📸 Preview
Coming soon: screenshots / demo gif

📡 Roadmap
✅ Multi-room support

✅ Modular monorepo

🔄 Persist chat history (DB integration)

🔄 Authentication + user avatars

🔄 Deployment with HTTPS/WSS

📌 License
MIT

yaml
Copy code

---

## 📝 Short Repo Description
> Full-stack realtime chat app using WebSockets. Backend (Node.js + WS) on Render, frontend (Next.js + Tailwind) on Vercel.

---

## 💼 LinkedIn Post (Combined Project)
🚀 Excited to share my latest **full-stack project** → a realtime chat app powered by **WebSockets**!  

🔹 **Backend** → Node.js, Express, TypeScript, WS (deployed on Render)  
🔹 **Frontend** → Next.js 15, TailwindCSS, TypeScript (deployed on Vercel)  
🔹 **Features** → Room-based messaging, connect/disconnect controls, clean modular UI  


This project was a deep dive into **WebSocket connections**, handling **realtime messaging**, and deploying a **monorepo (backend + frontend)** to production.  

Next up: chat persistence, auth, and richer UI features 👀  

#WebSockets #Nextjs #TypeScript #TailwindCSS #FullStack #Render #Vercel  

---
