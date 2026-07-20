# ThinkBoard

ThinkBoard is a full-stack note-taking app built with the MERN stack. It lets you create, edit, read, and delete notes through a React frontend and an Express/MongoDB backend, with rate limiting powered by Upstash Redis.

## Features

- Create, update, and delete notes
- View note details in a clean responsive UI
- REST API built with Express and Mongoose
- Rate limiting with Upstash Redis
- Separate frontend and backend apps for easier development and deployment

## Tech Stack

- Frontend: React, Vite, React Router, Axios, Tailwind CSS, DaisyUI
- Backend: Node.js, Express, Mongoose, Upstash Redis, dotenv
- Database: MongoDB

## Folder Structure

```text
thinkboard/
├── package.json
├── README.md
├── backend/
│   ├── package.json
│   ├── server.js
│   └── src/
│       ├── server.js
│       ├── config/
│       │   ├── db.js
│       │   └── upstash.js
│       ├── controllers/
│       │   └── notesController.js
│       ├── middleware/
│       │   └── rateLimiter.js
│       ├── models/
│       │   └── Note.js
│       └── routes/
│           └── notesRoutes.js
└── frontend/
    ├── package.json
    ├── vite.config.js
    ├── tailwind.config.js
    ├── postcss.config.js
    ├── eslint.config.js
    ├── index.html
    ├── public/
    └── src/
        ├── App.jsx
        ├── main.jsx
        ├── index.css
        ├── components/
        │   ├── Navbar.jsx
        │   ├── NoteCard.jsx
        │   ├── NotesNotFound.jsx
        │   └── RateLimitedUI.jsx
        ├── lib/
        │   ├── axios.js
        │   └── utils.js
        └── pages/
            ├── CreatePage.jsx
            ├── HomePage.jsx
            └── NoteDetailPage.jsx
```

## Environment Variables

Create a `.env` file in `backend/`:

```env
MONGO_URI=<your_mongo_uri>
UPSTASH_REDIS_REST_URL=<your_redis_rest_url>
UPSTASH_REDIS_REST_TOKEN=<your_redis_rest_token>
NODE_ENV=development
```

## Run Locally

### Backend

```bash
cd backend
npm install
npm run dev
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

## Root Scripts

From the project root, you can also use:

```bash
npm run build
npm start
```

## Notes

- `backend/server.js` is a compatibility shim that forwards to `backend/src/server.js`.
- The backend requires MongoDB and Upstash env vars to start successfully.
