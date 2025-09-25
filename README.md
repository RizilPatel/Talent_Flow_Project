# TalentFlow
TalentFlow is a hiring platform designed to simplify recruitment for HR teams and hiring managers. It enables managing job listings, tracking candidate progress through stages, creating and taking assessments, and analyzing hiring metrics via an interactive dashboard with data export capabilities.
Visit here : https://talent-flow-project.vercel.app


## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)a
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Architecture](#architecture)

## Features

- **Dashboard**: Overview of jobs and key hiring metrics.
- **Job Management**: Create, view, and manage job listings.
- **Candidate Tracking**: Visualize candidate progress through all hiring stages.
- **Assessments**: Build and take assessments for job applicants.
- **Analytics**: Interactive charts (pipeline, velocity, scores, top jobs) with CSV export.
- **Theme Toggle**: Seamless light/dark mode, persisted in `localStorage`.
- **Global Search**: Search jobs, candidates, and assessments.
- **Responsive Design**: Mobile-friendly UI using Tailwind CSS.
- **Mocked API**: MSW simulates backend endpoints for development.

## Tech Stack

- **Frontend**: React.js (18+), TypeScript
- **Build Tool**: Vite
- **Routing**: React Router (6+)
- **Styling**: Tailwind CSS (OKLCH colors, dark mode)
- **UI Components**: Shadcn/UI
- **Icons**: Lucide React
- **Charts**: Recharts
- **API Mocking**: MSW (Mock Service Worker)
- **Theme Management**: Custom React Context
- **Utilities**: `clsx`, `tailwind-merge`
- **Linting/Formatting**: ESLint, Prettier

## Project Structure

```
/miniHire/
├── public/
│   ├── index.html
│   └── mockServiceWorker.js
├── src/
│   ├── components/
│   │   ├── assessments/
│   │   ├── candidates/
│   │   ├── jobs/
│   │   ├── layout/
│   │   ├── ui/
│   │   └── ThemeProvider.tsx
│   ├── hooks/
│   ├── lib/
│   ├── mocks/
│   ├── styles/
│   ├── App.tsx
│   ├── main.tsx
│   ├── AnalyticsPage.tsx
│   ├── AssessmentsPage.tsx
│   ├── TakeAssessmentPage.tsx
│   ├── AssessmentBuilder.tsx
│   ├── NotFoundPage.tsx
│   ├── HomePage.tsx
│   └── index.tsx
├── tailwind.config.js
├── vite.config.ts
├── package.json
├── .env
└── README.md
```

## Setup Instructions

### Prerequisites

- **Node.js**: v18 or higher
- **npm**: v9 or higher

### Installation

1. **Clone the Repository**
  ```bash
  git clone <repository-url>
  cd miniHire
  ```

2. **Install Dependencies**
  ```bash
  npm install
  ```

3. **Set Up Environment**
  - Create a `.env` file in the root:
    ```
    VITE_API_URL=http://localhost:5173
    ```

4. **Initialize MSW**
  ```bash
  npx msw init public/ --save
  ```

5. **Run the Development Server**
  ```bash
  npm run dev
  ```
  Open [http://localhost:5173](http://localhost:5173) in your browser.

6. **Build for Production**
  ```bash
  npm run build
  npm run preview
  ```

### Scripts

- `npm run dev`: Start the development server
- `npm run build`: Build for production
- `npm run preview`: Preview the production build
- `npm run lint`: Run ESLint
- `npm run format`: Run Prettier

## Architecture

### Frontend

- **React.js**: Component-based architecture with TypeScript.
- **React Router**: Client-side routing (`/`, `/jobs`, `/candidates`, `/assessments`, `/analytics`).
- **ThemeProvider**: Custom React Context for theme, toggling Tailwind’s `dark` class and persisting in `localStorage`.
- **Shadcn/UI**: Reusable, accessible UI components.
- **Tailwind CSS**: Utility-first styling with OKLCH color support and dark mode.
- **Recharts**: Analytics charts (Bar, Pie, Line).

### Data Layer

- **DatabaseService**: Mock data layer (`src/lib/db.ts`) for jobs, candidates, assessments.
- **MSW**: Simulates API endpoints with realistic delays and error rates.
- **Analytics**: Local processing for pipeline, velocity, scores, and top jobs.

### Key Components

- **Navigation**: Responsive navbar with routing and theme toggle.
- **AnalyticsPage**: Visualizes metrics and exports CSV.
- **ThemeProvider**: Manages and persists theme state.

