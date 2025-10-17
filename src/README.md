# Mergington High School Activities

A comprehensive web application that enables students to discover and register for extracurricular activities, with teacher authentication and management capabilities.

## Features

### For Students
- **Browse Activities**: View all available extracurricular activities with detailed information
- **Advanced Filtering**: Filter activities by day of the week and time of day (client-side), with backend support for day and time-based queries
- **Search Functionality**: Search for specific activities by name (client-side filtering)
- **Activity Details**: View comprehensive information including schedules, descriptions, and current participant counts
- **Registration**: Sign up for activities (requires teacher authentication)

### For Teachers
- **Secure Login**: Role-based authentication system for teachers and administrators
- **Student Management**: Register and unregister students for activities
- **Activity Oversight**: View and manage student participation across all activities

### Technical Features
- **Modern Web Interface**: Responsive design with intuitive user experience
- **RESTful API**: FastAPI backend with comprehensive API documentation
- **Database Integration**: MongoDB for persistent data storage
- **Real-time Updates**: Dynamic content loading and filtering (category and search filtering handled client-side, day/time filtering supported server-side)
- **Authentication System**: Secure teacher login with SHA-256 password hashing

## Activity Categories

The system supports multiple activity categories:
- **Sports**: Soccer Team, Basketball Team, Morning Fitness
- **Arts**: Art Club, Drama Club
- **Academic**: Math Club, Debate Team, Programming Class
- **Community**: Various community service activities
- **Technology**: Weekend Robotics Workshop, Science Olympiad
- **Special Interest**: Chess Club, Manga Maniacs, and more

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/activities` | Get all activities with optional filtering by day and time |
| GET | `/activities/days` | Get list of all days that have activities scheduled |
| POST | `/activities/{activity_name}/signup` | Register a student for an activity (requires teacher auth) |
| POST | `/activities/{activity_name}/unregister` | Remove a student from an activity (requires teacher auth) |
| POST | `/auth/login` | Teacher login authentication |
| GET | `/auth/check-session` | Validate teacher session |

## Development Guide

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).

### Quick Start

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the application:
   ```bash
   uvicorn src.app:app --host 0.0.0.0 --port 8000
   ```
   
   Or from the project root:
   ```bash
   python -m uvicorn src.app:app --host 0.0.0.0 --port 8000
   ```

3. Access the application:
   - Website: http://localhost:8000
   - API Documentation: http://localhost:8000/docs

### Authentication

The system includes pre-configured teacher accounts:
- **Ms. Rodriguez** (mrodriguez): Art teacher
- **Mr. Chen** (mchen): Chess club coordinator  
- **Principal Martinez** (principal): Administrator

> **Note**: All data is stored in MongoDB. The system initializes with sample activities and teacher accounts on first run.
