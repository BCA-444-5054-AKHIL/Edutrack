# EduTrack

EduTrack is a full-stack education project tracking system with a React/Vite frontend and an Express/Node backend. It supports user authentication, project management, submissions, grading, analytics, leaderboards, badges, notifications, and role-based dashboards.
 live link - https://edutrack-frontend-tan.vercel.app/landingpage.html

## Tech stack

- Frontend
  - React 19
  - Vite
  - React Router DOM
  - Axios
  - Chart.js
  - DOMPurify
  - Monaco editor integration
- Backend
  - Node.js 20.x
  - Express
  - Sequelize ORM
  - PostgreSQL driver (`pg`)
  - JWT authentication
  - CORS, Helmet, rate limiting, validation
  - Email/notification support via SendGrid, AWS SDK, Nodemailer

## Project structure

- `backend/`
  - `server.js` - backend server entry point
  - `app.js` - Express app setup, middleware, routes
  - `config/database.js` - Sequelize and database connection
  - `controllers/` - business logic handlers
  - `models/` - Sequelize models
  - `routes/` - API route definitions
  - `middleware/` - auth, validation, rate limiting
- `frontend/`
  - `src/main.jsx` - React app bootstrap
  - `src/App.jsx` - route definitions
  - `src/components/` - dashboards, auth, editor, shared UI
  - `src/services/` - API and auth helpers
  - `public/` - static frontend assets

## Local installation

### Prerequisites

- Node.js 20.x
- PostgreSQL database
- npm

### Setup backend

1. Open a terminal in `backend/`
2. Install dependencies:
   ```bash
   cd backend
   npm install
   ```
3. Create an environment file or copy `import.env` to `.env` and update values:
   - `DATABASE_URL` or connection details for PostgreSQL
   - `JWT_SECRET`
   - `SENDGRID_API_KEY`, `EMAIL_FROM`, or other notification settings if used
   - any other required secret keys
4. Start the backend server:
   ```bash
   npm run dev
   ```

The backend defaults to `server.js` and exposes the API routes under `/api`.

### Setup frontend

1. Open a terminal in `frontend/`
2. Install dependencies:
   ```bash
   cd frontend
   npm install
   ```
3. Start the frontend development server:
   ```bash
   npm run dev
   ```

The frontend is served by Vite and will typically run on `http://localhost:5173`.

## Running the app

1. Start the backend.
2. Start the frontend.
3. Open the frontend URL in your browser and use the app.

## Notes

- The frontend calls the backend API for authentication, project data, submissions, grading, and analytics.
- Protected routes are enforced in the frontend by `ProtectedRoute.jsx`.
- Backend routes are grouped under `routes/` and guarded with authentication middleware.

## Helpful commands

- Backend development: `cd backend && npm run dev`
- Frontend development: `cd frontend && npm run dev`
- Frontend build: `cd frontend && npm run build`
