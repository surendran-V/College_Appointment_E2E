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

---


### API Testing with Postman

##### API Endpoints

Set the {{url}} as http://127.0.0.1:8000
1. Register a user (student or professor).
   
   ##### POST {{url}}/api/auth/register

   ##### Body :
   ```
   {
     "name": "Steve Smith",
     "email": "steve.smith@example.com",
     "password": "securePass456",
     "role": "professor"
   }
   ```
   ##### Response:
   ```
   {  
     "token": "JWT_TOKEN"  
   }
   ```
2. Logs in a user (student or professor).
   
   ##### POST {{url}}/api/auth/login
   ##### Body : 
   ```
   {  
     "email": "user@example.com",  
     "password": "password123"  
   }
   ```
   ##### Response :
   ```
   {  
     "token": "JWT_TOKEN"  
   }  
   ```
   
3. Creates a new availability slot for a professor.(only professeors)
   ##### POST {{url}}/api/availability
   ##### Headers : Authorization: Bearer <JWT_TOKEN>
   ##### Body :
   ```
      {  
     "date": "2024-01-20",  
     "startTime": "10:00",  
     "endTime": "11:00"  
      }
   ```
4. Get Available Slots
   ##### GET {{url}}/api/availability
  
   ##### Query Parameters: professorId=<PROFESSOR_ID>
   ##### Headers: Authorization: Bearer <JWT_TOKEN>

5. Book Appointment (Student Only)

   ##### POST /api/appointments/book
   ##### Headers: Authorization: Bearer <JWT_TOKEN>
   ##### Body:
   ```
   {  
     "availabilityId": "AVAILABILITY_ID",  
     "professorId": "PROFESSOR_ID"  
   }
   ```
6. View Appointments
   
   ##### GET /api/appointments
   ##### Headers: Authorization: Bearer <JWT_TOKEN>
   
7. Cancel Appointment (Professor Only)
   id is the appointment id, add that to path variable

   ##### DELETE /api/appointments/:id/cancel
   
   ##### Headers: Authorization: Bearer <JWT_TOKEN>

---

### Automated End-to-End Test

## Steps to Run
1. Install Test Dependencies:
   ```
   npm install --save-dev mongodb-memory-server jest supertest
   ```
3. Run Tests:
   ```
   npm test --appointmentFlow.test.js
   ```
# Test Coverage
The test validates the following flow:

- Student A1 logs in.
- Professor P1 logs in and adds time slots.
- Student A1 books an appointment with Professor P1.
- Student A2 books another slot with Professor P1.
- Professor P1 cancels Student A1's appointment.
- Student A1 checks their appointments to confirm cancellation.

### Challenges and Solutions 🧩
- Authentication Handling
Challenge: Ensuring secure authentication for both students and professors.
Solution: Implemented JWT authentication with a middleware to protect API routes.
- Error Handling
Challenge: Managing various error scenarios like invalid data, unauthorized access, etc.
Solution: Implemented custom error messages and status codes to improve the user experience.

### Future Improvements 🚀
- User Roles: Extend functionality to include different user roles (e.g., admin).
- UI Frontend: Create a React or Angular frontend for a user-friendly interface.
- Real-Time Updates: Add WebSocket support for real-time appointment updates.
### Video Demonstration 📽️

 1. Automated test case running - https://drive.google.com/file/d/1OCKa3u44LMrYwrXNiHnyyXwCsVZV9l8d/view?usp=drive_link
 2. Demonstrating the user flow manually through Postman - https://drive.google.com/file/d/1C-LJ4sttd-T7RdQzpF4y5GzRsYVhHvZr/view?usp=drive_link

   
   

