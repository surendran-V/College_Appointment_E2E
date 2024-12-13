# Appointment System

This project demonstrates an Appointment System designed for students and professors. The system allows professors to create available time slots, students to book appointments, and both users to view and cancel their appointments. The backend API is built using Node.js, Express, and MongoDB. The system's API user flow is tested using Postman and Supertest.

## Features 🚀

- **User Authentication**: Login system for both students and professors using JWT tokens.
- **Professor Availability**: Professors can create time slots where they are available for appointments.
- **Appointment Booking**: Students can book appointments with professors based on available slots.
- **Appointment Management**: Users can view their appointments and cancel them if needed.
- **API Testing**: Postman for manual API testing, Supertest for automated API tests.
- **Error Handling**: Provides descriptive error messages for invalid inputs, unauthorized access, or processing failures.

## Technologies Used 🛠️

The following technologies were used to build this solution:

### Backend
- **Node.js**: JavaScript runtime for the backend.
- **Express**: Web framework for the backend API.
- **MongoDB**: Database to store user and appointment data.
- **Mongoose**: ODM for MongoDB to manage data models.
- **JWT (JSON Web Token)**: For authentication and securing API routes.
- **Postman**: For manual API testing.
- **Supertest**: For automated API testing with Jest.

### Testing
- **Supertest**: Used to make HTTP requests in automated tests for API validation.

## Setup and Installation

### Prerequisites
- Node.js (>=14)
- MongoDB running locally or on a cloud service (e.g., MongoDB Atlas)
- Postman for API testing
- A code editor (e.g., Visual Studio Code)

### Project Structure
```
src/  
├── config/            # Database and configuration files  
├── controllers/       # API endpoint logic  
├── middleware/        # Authentication and authorization middleware  
├── models/            # MongoDB schemas  
├── routes/            # API routes  
├── services/          # Business logic  
├── tests/             # E2E test cases  
└── utils/             # Helper functions (e.g., token generation)
```

### Backend Setup

1. Clone the repository:
   ```
   git clone https://github.com/surendran-V/College-Appointment-E2E.git
   cd College-Appointment-System-Backend-API-Development
   ```
2. Install Node.js dependencies:
   ```
   npm install

   ```
3. Set up your environment variables: Create a .env file and add the following configuration:
   ```
   PORT=8000
   MONGO_URI=your_mongo_db_connection_string
   JWT_SECRET=your_jwt_secret_key
   ```
4. Start the backend server:
   ```
   npm run dev
   ```
   The server will run on http://127.0.0.1:8000
   
### API Testing with Postman

## API Endpoints

Set the {{url}} as http://127.0.0.1:8000
1. Register a user (student or professor).
   POST {{url}}/api/auth/register

   Body :
   ```
   {
     "name": "Steve Smith",
     "email": "steve.smith@example.com",
     "password": "securePass456",
     "role": "professor"
   }
   ```
   Response
3. Logs in a user (student or professor).
   POST {{url}}/api/auth/login
   ```
   npm install

   ```
4. Creates a new availability slot for a professor.
   POST {{url}}/api/availability
   ```
   PORT=8000
   MONGO_URI=your_mongo_db_connection_string
   JWT_SECRET=your_jwt_secret_key
   ```
5. POST {{url}}/api/availability
   ```
   npm run dev
   ```
6. POST {{url}}/api/appointments/book
   ```
   npm run dev
   ```
7. GET {{url}}/api/appointments
   ```
   npm run dev
   ```
8. DELETE {{url}}/api/appointments/:id/cancel
   ```
   ```
   
   

