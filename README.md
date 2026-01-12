# More Weight

A personalized workout routine generator and tracking application that creates custom training programs based on user preferences, experience level, and training goals.

## What It Does

More Weight is a fitness application that:

- **Generates Personalized Routines**: Creates custom workout splits based on user inputs including experience level, training frequency, muscle group preferences, and time constraints
- **Tracks Workouts**: Allows users to log sets, reps, weight, and RPE (Rate of Perceived Exertion) during workouts
- **Monitors Progress**: Provides progress tracking and workout history for individual movements
- **Adapts to Preferences**: Customizes routines based on muscle bias (e.g., upper vs lower chest, quads vs hamstrings), training style, and available time

The app uses a sophisticated algorithm that calculates muscle stimulus, optimizes movement sequencing, and balances training volume across workout days to create effective, personalized routines.

## Tech Stack

### Frontend
- **React 18.3** - UI framework
- **React Router 6** - Client-side routing
- **Bootstrap 5** - UI styling components
- **Axios** - HTTP client for API requests
- **Math.js** - Mathematical calculations

### Backend
- **Node.js** - Runtime environment
- **Express 4** - Web framework
- **MongoDB** - Primary database (via Mongoose)
- **bcrypt** - Password hashing for authentication
- **Jest** - Testing framework

### Architecture
- **RESTful API** - Backend exposes REST endpoints for all operations
- **MVC Pattern** - Models (Mongoose schemas), Routes (Express), and Business Logic (Classes)
- **Client-Server Architecture** - React SPA communicates with Express API

## Architecture Overview

The application follows a client-server architecture:

### Frontend Structure
- **Pages**: Main application views (Welcome, Login, Workout, Track, Profile, Input pages)
- **Components**: Reusable UI components (FooterMenu, ProgressBar, Dropdown, etc.)
- **Utils**: Static data and helper functions
- **Routing**: React Router handles navigation between pages

### Backend Structure
- **Routes**: Express route handlers for API endpoints (`/login`, `/set-routine`, `/log-set`, etc.)
- **Models**: Mongoose schemas for Users, Logs, Inputs, and Features
- **Business Logic**: Core algorithm in `RoutineClass` that:
  - Calculates ideal muscle stimulus based on experience and preferences
  - Generates movement sequences optimized for muscle group targeting
  - Balances training volume across workout days
  - Optimizes rest times and set organization
  - Fits routines into specified time constraints

### Key Features
- **User Authentication**: Secure login/signup with password hashing
- **Routine Generation**: Complex algorithm that considers:
  - Experience level (beginner/intermediate/advanced)
  - Training frequency and split preferences
  - Muscle group bias and targeting
  - Time constraints
  - Movement sequencing and rest periods
- **Workout Tracking**: Real-time logging of sets with weight, reps, and RPE
- **Progress Monitoring**: Historical tracking of workout performance

## How It's Used

### For New Users
1. **Sign Up**: Create an account with username and password
2. **Input Survey**: Complete a multi-step questionnaire:
   - Experience level (beginner/intermediate/advanced)
   - Training days per week
   - Muscle group preferences and bias
   - Base movements (chest, back, legs)
   - Split selection (e.g., Push/Pull/Legs, Upper/Lower)
   - Training style preferences
   - Number of sets per movement
   - Available time per workout
   - Accessory preferences
   - Specific movement selections for each muscle group
3. **Receive Routine**: Get a personalized workout routine generated based on inputs
4. **Start Training**: Begin following the generated routine

### For Existing Users
1. **Login**: Access account with credentials
2. **View Workout**: See today's workout based on the day of the week
3. **Track Sets**: Log weight, reps, and RPE for each set during workouts
4. **View Progress**: Check workout history and track performance over time
5. **Edit Routine**: Modify or create new routines as needed

### Development Setup

#### Prerequisites
- Node.js (v14 or higher)
- MongoDB database
- npm or yarn

#### Backend Setup
```bash
cd backend
npm install
# Create a .env file with:
# MONGO_URI=your_mongodb_connection_string
# PORT=3000
npm start
```

#### Frontend Setup
```bash
cd frontend
npm install
npm start
# Runs on http://localhost:3000 (or next available port)
```

#### Running Tests
```bash
cd backend
npm test
```

### Project Status

The application is fully functional but not currently hosted. It can be run locally for development and testing purposes. The codebase includes:
- Complete user authentication system
- Full routine generation algorithm
- Workout tracking functionality
- Progress monitoring features
- Responsive mobile-first design

