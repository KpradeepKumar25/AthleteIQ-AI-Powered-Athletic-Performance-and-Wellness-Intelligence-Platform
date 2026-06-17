# Fitness App Backend

This is the backend server for the fitness tracking application. It provides APIs for logging workouts and measurements, and generates AI-powered insights based on the user's fitness data.

## Features

- Workout tracking (planned vs. actual performance)
- Body measurements and fitness parameters tracking
- AI-powered insights generation
- RESTful API endpoints
- SQLite database (configurable to use other databases)

## Setup

1. Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the backend directory with the following content:

```
DATABASE_URL=sqlite:///fitness.db
```

4. Run the application:

```bash
python app.py
```

The server will start on `http://localhost:5000`

## API Endpoints

### Workouts

- `POST /api/workout`

  - Log a new workout
  - Returns workout data and AI insight

- `GET /api/workouts/<user_id>`
  - Get all workouts for a user
  - Returns list of workouts

### Measurements

- `POST /api/measurement`

  - Log new body measurements
  - Returns measurement data and AI insight

- `GET /api/measurements/<user_id>`
  - Get all measurements for a user
  - Returns list of measurements

### Insights

- `GET /api/insights/<user_id>`
  - Get AI-generated insights for a user
  - Returns comprehensive fitness analysis

## Data Models

### Workout

- user_id
- date
- workout_type
- planned_duration
- actual_duration
- planned_distance
- actual_distance
- planned_pace
- actual_pace
- heart_rate_avg
- calories_burned

### Measurement

- user_id
- date
- weight
- bmi
- vo2_max
- push_ups

## AI Analysis

The backend includes an AI analysis module that:

- Analyzes workout trends
- Tracks progress in measurements
- Generates personalized insights
- Provides actionable feedback

## Security

- CORS enabled for frontend integration
- Input validation on all endpoints
- Error handling for all operations
- Data privacy compliance

## Development

To run in development mode:

```bash
export FLASK_ENV=development  # On Windows: set FLASK_ENV=development
python app.py
```
