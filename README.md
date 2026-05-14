# Productr (Assignment)

UI and flows follow the design spec:

**[Assignment — Figma](https://www.figma.com/design/jz1CdCk9aaW5itU99sC6uB/Assignment-_Dev?node-id=1-770)**

This repository is a **MERN-style** app (React + Vite frontend, Node + Express + MongoDB backend). It is **not** a Docker / Nginx / MySQL three-tier demo.

## Project structure

- **`backend/`** – Express API (OTP auth, JWT, products)
- **`frontend/`** – React + Vite + Tailwind UI

## Setup

### Backend

```bash
cd backend
npm install
```

Copy `backend/.env.example` to `backend/.env` and fill in values:

- **`MONGODB_URI`** – MongoDB connection string (local or Atlas)
- **`SMTP_EMAIL`**, **`SMTP_PASSWORD`** – Gmail + [App Password](https://myaccount.google.com/apppasswords) for sending OTP
- **`JWT_SECRET`** – secret for signing JWTs
- **`PORT`** – API port (default `5000`)

### Frontend

```bash
cd frontend
npm install
```

Optional: copy `frontend/.env.example` to `frontend/.env` if you need a custom API base URL or Cloudinary keys for product images.

## Run

**Terminal 1 – backend**

```bash
cd backend
npm run dev
```

**Terminal 2 – frontend**

```bash
cd frontend
npm run dev
```

- App: http://localhost:5173 (or the next free port)
- API: http://localhost:5000

## Flow

1. Enter email → **Send OTP** → code sent via Gmail
2. Enter OTP → **Verify OTP** → JWT stored; dashboard and products routes are protected
