# Event Management and Analytical Portal

## Project Overview

The **Event Management and Analytical Portal** is a web-based application designed to simplify the process of creating, managing, registering, and analyzing events.

The system provides a centralized platform where **administrators/organizers** can manage events, participants can register for events, and event-related data can be stored and analyzed efficiently.

The project combines **database management, backend API development, multi-framework technologies, microservices concepts, and deployment practices** to provide a complete event management solution.

---

## Problem Statement

Managing college and organizational events manually can result in:

- Difficulty maintaining event information
- Duplicate or inconsistent registration records
- Difficulty tracking organizers and participants
- Time-consuming registration management
- Lack of centralized event data
- Difficulty generating useful analytical information
- Limited monitoring of event participation

Therefore, there is a need for a centralized system that can efficiently manage event information, organizers, registrations, and analytical data.

---

## Proposed Solution

The Event Management and Analytical Portal provides a centralized digital platform for managing the complete event lifecycle.

The system allows users to:

- Create and manage events
- Maintain organizer information
- View available events
- Register for events
- Track registrations
- Store participant information
- Analyze event participation
- Retrieve information through backend APIs
- Manage event-related data efficiently

---

## Features

### User Management

- User registration and login
- User information management
- Role-based access for different users

### Event Management

- Create new events
- Update event information
- Delete events
- View available events
- Store event details such as date, venue, and description

### Organizer Management

- Add organizers
- Store organizer details
- Associate organizers with events
- Manage organizer information

### Registration Management

- Register participants for events
- Track event registrations
- View registration information
- Prevent duplicate registrations where applicable

### Analytics

The portal can be used to analyze:

- Number of registrations per event
- Event participation
- Organizer activity
- Event popularity
- Registration trends

### Backend APIs

REST APIs are used to communicate between the frontend and backend components.

---

## System Architecture

```text
                    ┌─────────────────────┐
                    │       User          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      Frontend       │
                    │   Web Application   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     Backend API     │
                    │  Business Logic     │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┴─────────────┐
                 ▼                           ▼
        ┌─────────────────┐        ┌─────────────────┐
        │    Database     │        │    Analytics    │
        │ Event & User    │        │ Registration    │
        │ Information     │        │ Analysis        │
        └─────────────────┘        └─────────────────┘
```

---

## Main Modules

### 1. User Module

Handles user registration, authentication, and user information.

### 2. Event Module

Responsible for creating, updating, viewing, and deleting events.

### 3. Organizer Module

Maintains organizer information such as:

- Organizer ID
- Name
- Email
- Department

### 4. Registration Module

Manages participant registrations and maintains relationships between users and events.

### 5. Analytics Module

Processes stored event data to provide useful information about registrations and participation.

### 6. API Module

Provides communication between the frontend and backend using REST APIs.

### 7. Deployment and Monitoring Module

Supports deployment, monitoring, and maintenance of the application.

---

## Database Design

The system uses databases to store and manage event-related information.

### Main Entities

```text
Users
  │
  │
  ▼
Registrations ───────► Events
                          │
                          │
                          ▼
                      Organizers
```

### Example Tables

#### Users

| Field | Description |
|---|---|
| user_id | Unique user identifier |
| name | User name |
| email | User email |
| password | User authentication information |
| role | User role |

#### Events

| Field | Description |
|---|---|
| event_id | Unique event identifier |
| event_name | Name of event |
| description | Event description |
| date | Event date |
| venue | Event location |
| organizer_id | Associated organizer |

#### Organizers

| Field | Description |
|---|---|
| organizer_id | Unique organizer identifier |
| name | Organizer name |
| email | Organizer email |
| department | Organizer department |

#### Registrations

| Field | Description |
|---|---|
| registration_id | Unique registration identifier |
| user_id | Registered user |
| event_id | Selected event |
| registration_date | Date of registration |

---

## Technologies Used

### Frontend

- HTML
- CSS
- JavaScript
- React, if used

### Backend

- Node.js
- Express.js

### Database

- MySQL
- MongoDB where applicable

### API

- REST API

### Development Tools

- Visual Studio Code
- MySQL
- MongoDB / MongoDB Shell
- Git
- GitHub
- Postman

### Versions Used

```text
Node.js   : v24.15.0
npm       : v11.12.1
MySQL     : 8.0.46
mongosh   : v2.10.0
```

---

## Project Structure

```text
Event-Management-Analytical-Portal/
│
├── frontend/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── components/
│
├── backend/
│   ├── server.js
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   └── middleware/
│
├── database/
│   ├── schema.sql
│   ├── tables.sql
│   └── sample_data.sql
│
├── analytics/
│
├── screenshots/
│
├── README.md
└── package.json
```

> Modify the folder names above if your actual project structure is different.

---

## Installation and Setup

### 1. Clone the Repository

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
```

### 2. Navigate to the Project

```bash
cd Event-Management-Analytical-Portal
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure the Database

Create the required database and tables using the SQL files provided in the `database` folder.

Example:

```sql
CREATE DATABASE event_management;
```

Then select the database:

```sql
USE event_management;
```

Execute the required table creation and sample-data scripts.

### 5. Configure Environment Variables

Create a `.env` file in the backend directory.

```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=event_management
```

Do not upload passwords or other sensitive credentials to GitHub.

### 6. Start the Backend

```bash
npm start
```

or, if using a development script:

```bash
npm run dev
```

### 7. Open the Application

Open the frontend in your browser or use the configured development server.

---

## API Examples

### Events

```text
GET     /api/events
GET     /api/events/:id
POST    /api/events
PUT     /api/events/:id
DELETE  /api/events/:id
```

### Organizers

```text
GET     /api/organizers
POST    /api/organizers
PUT     /api/organizers/:id
DELETE  /api/organizers/:id
```

### Registrations

```text
GET     /api/registrations
POST    /api/registrations
DELETE  /api/registrations/:id
```

---

## Sample Event Data

| Event | Registrations |
|---|---:|
| Tech Fest 2026 | 4 |
| Web Development Workshop | 3 |
| Cultural Fest | 3 |
| AI and Machine Learning Seminar | 2 |

This sample data can be used to demonstrate the analytical functionality of the portal.

---

## Course Outcome Mapping

The project demonstrates the following course outcomes:

| CO | Area | Project Implementation |
|---|---|---|
| CO1 | Relational Database Engineering | Database schema, tables, relationships |
| CO2 | Database Engineering | CRUD operations and data management |
| CO3 | Backend API Engineering | REST API development |
| CO4 | Multi-Framework Backend Engineering | Integration of frontend and backend technologies |
| CO5 | Microservices Engineering | Modular service-based architecture |
| CO6 | Deployment, Observability & Delivery | Deployment, monitoring and delivery practices |

---

## Security Considerations

The application should follow basic security practices such as:

- Password protection
- Input validation
- Authentication and authorization
- Prevention of SQL injection
- Secure API endpoints
- Environment variables for credentials
- Avoiding sensitive information in source code

---

## Future Scope

The project can be enhanced with:

- Online payment integration
- QR-code based event check-in
- Email notifications
- WhatsApp notifications
- Event recommendation system
- Advanced dashboards
- Attendance tracking
- AI-based event analytics
- Cloud deployment
- Real-time notifications
- Mobile application
- Advanced role-based access control

---

## Advantages

- Centralized event management
- Reduced manual work
- Faster registration process
- Better organization of event data
- Easy organizer management
- Improved registration tracking
- Data-driven event analysis
- Scalable architecture

---

## Testing

The application can be tested using:

- Unit testing
- API testing
- Database testing
- Integration testing
- User interface testing
- Authentication testing

Postman can be used to test REST API endpoints.

---

## Project Team

**Project Title:**  
Event Management and Analytical Portal

**Domain:**  
Database Management / Web Application Development

**Technologies:**  
Node.js, Express.js, MySQL, MongoDB, HTML, CSS, JavaScript

---

## License

This project was developed for academic purposes as part of a college project.

---

## Conclusion

The **Event Management and Analytical Portal** provides a centralized solution for managing events, organizers, registrations, and event-related analytics. By integrating database management with backend APIs and modern web technologies, the system demonstrates how event management processes can be digitized, organized, and analyzed efficiently.
