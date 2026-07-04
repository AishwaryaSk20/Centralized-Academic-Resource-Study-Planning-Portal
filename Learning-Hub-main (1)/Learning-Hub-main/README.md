# Study Platform

A centralized study companion for planning schedules, organizing resources, tracking progress, and preparing for exams and interviews.

## Project Overview

This project solves the problem of managing academic preparation across multiple disconnected tools. Instead of keeping study plans, notes, mock tests, and resource links in separate places, it brings them into one centralized experience.

It is aimed at students who want a structured way to organize their learning, monitor progress, and stay consistent over time. The platform is especially useful for exam preparation, interview readiness, and day-to-day study planning.

A practical use case is a student preparing for placements or competitive exams who needs to track study schedules, save references, review notes, complete mock tests, and monitor readiness in one place.

## Features

- ✅ User registration, login, and profile access
- ✅ Study schedule creation and task tracking
- ✅ Resource management for academic and interview materials
- ✅ Topic-level progress tracking and readiness check-ins
- ✅ Notes with bookmarking and revision support
- ✅ Mock test practice and submission history
- ✅ Study analytics, dashboard summaries, and activity insights
- ✅ Streaks, badges, and gamified progress tracking
- ✅ Notifications for study-related updates
- ✅ Interview preparation modules and experience pages

## Tech Stack

| Category | Technology |
|----------|------------|
| Backend | FastAPI, Uvicorn, Pydantic |
| Frontend | React, Vite, React Router |
| Database | MongoDB |
| Charts | Chart.js, Recharts |
| Authentication | JWT-based authentication with Python-Jose and Passlib |
| Other Libraries | Axios, React Hot Toast, React Icons, PyMongo |

## Project Architecture

The application follows a simple layered flow:

User
↓
React + Vite Frontend
↓
FastAPI Routes
↓
Business Logic and Validation
↓
MongoDB Collections
↓
JSON Responses and UI Updates

### Layers

- Frontend: React pages and reusable components for the dashboard, schedules, resources, notes, analytics, tests, notifications, gamification, and interview preparation.
- API Layer: FastAPI routers handle authentication, planning, resources, progress, tests, analytics, notes, notifications, readiness, and gamification.
- Data Layer: MongoDB stores user data, schedules, notes, progress records, test submissions, study logs, and notification history.

## Folder Structure

```text
study-platform/
├── backend/
│   ├── routers/
│   ├── main.py
│   ├── database.py
│   ├── schemas.py
│   ├── requirements.txt
│   └── starter_data.py
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   ├── components/
│   │   ├── context/
│   │   ├── data/
│   │   └── pages/
│   ├── package.json
│   └── vite.config.js
├── package.json
└── README.md
```

## Installation

### Prerequisites

- Python 3.10+
- Node.js 18+
- npm
- MongoDB running locally on port 27017

### 1. Clone the repository

```bash
git clone <repository-url>
cd study-platform
```

### 2. Set up the backend

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r backend/requirements.txt
```

Create a `.env` file in the project root with the following values:

```env
MONGO_DATABASE_URL=mongodb://localhost:27017
MONGO_DATABASE_NAME=studyplatform
```

Start the FastAPI backend:

```powershell
cd backend
uvicorn main:app --reload
```

The API will be available at `http://127.0.0.1:8000` and the docs at `http://127.0.0.1:8000/docs`.

### 3. Set up the frontend

Open a second terminal and run:

```powershell
cd frontend
npm install
npm run dev
```

The frontend will typically run at `http://127.0.0.1:5173`.

## Usage

1. Start MongoDB locally.
2. Launch the backend server.
3. Launch the frontend development server.
4. Open the frontend URL in your browser and register or log in.

## User Roles

The current application is centered around authenticated student users. There are no separate admin, teacher, or role-based permission tiers visible in the provided source.

## Database Design

The project uses MongoDB collections to store user-owned study data, including schedules, resources, progress, notes, test submissions, notifications, and gamification records.

Key collections include:

- users
- streaks
- badges
- user_badges
- notifications
- schedules and schedule_tasks
- resources
- subject_progress and topic_progress
- readiness_checkins
- notes
- mock_tests and test_submissions
- study_logs
- counters

## API Routes

The backend exposes route groups for:

- Authentication: `/api/auth/register`, `/api/auth/login`, `/api/auth/me`
- Schedules: `/api/schedules`
- Resources: `/api/resources`
- Progress: `/api/progress`
- Mock tests: `/api/tests`
- Readiness: `/api/readiness`
- Notes: `/api/notes`
- Gamification: `/api/gamification`
- Notifications: `/api/notifications`
- Analytics: `/api/analytics`

## Screenshots

![Dashboard](images/dashboard.png)

![Study Schedule](images/schedule.png)

![Progress Analytics](images/progress.png)

> [TODO] Add real screenshots for the main dashboard, study planner, and analytics views.

## Future Improvements

- [TODO] Add real screenshots and product visuals.
- [TODO] Add automated tests for backend and frontend flows.
- [TODO] Add deployment configuration for production hosting.

## Learning Outcomes

This repository demonstrates a full-stack application built with:

- FastAPI for backend API development
- React and Vite for the frontend experience
- MongoDB for document-based persistence
- JWT-based user authentication
- Responsive dashboard and analytics UI patterns

## License

[TODO] Add an open-source license file if you plan to publish this repository.

## Contact

[TODO] Add maintainer contact information.
