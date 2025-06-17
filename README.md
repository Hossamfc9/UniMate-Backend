# UniMate-Backend

![GitHub last commit](https://img.shields.io/github/last-commit/hossamfc9/uniMate-Backend)
![GitHub repo size](https://img.shields.io/github/repo-size/hossamfc9/uniMate-Backend)

The backend service for uniMate - a university collaboration platform connecting students, faculty, and resources.

## Features

- **User Authentication**: JWT-based secure authentication system
- **Resource Management**: CRUD operations for academic resources
- **Real-time Communication**: Socket.io for chat and notifications
- **University Integration**: Department/course management system
- **API Services**: RESTful endpoints for frontend applications
- **Data Analytics**: Student engagement metrics and insights

## Tech Stack

- **Framework**: Node.js / Express.js
- **Database**: MongoDB (with Mongoose ODM)
- **Authentication**: JSON Web Tokens (JWT)
- **Real-time**: Socket.io
- **Validation**: Joi
- **Testing**: Jest + Supertest
- **Containerization**: Docker
- **CI/CD**: GitHub Actions

## Getting Started

### Prerequisites
- Node.js v18+
- MongoDB Atlas account or local MongoDB instance
- npm v9+

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/hossamfc9/uniMate-Backend.git
   cd uniMate-Backend
