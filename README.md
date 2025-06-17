# UniMate-Backend

![GitHub last commit](https://img.shields.io/github/last-commit/hossamfc9/uniMate-Backend)
![GitHub repo size](https://img.shields.io/github/repo-size/hossamfc9/uniMate-Backend)

The backend service for uniMate - a university collaboration platform connecting students, faculty, and resources.

## Features

- **User Authentication**: JWT-based secure authentication system
- **Resource Management**: CRUD operations for Apartments
- **Student Management**: Students can book an apartment, room, bed for him or his friends, students can view all apartment images
   before booking.
   **Owner Management** Owners can add their apartments to be booked by students, accept or refuse students' requests.
## Tech Stack

- **Framework**: .NET / React.js(for frontend if included)
- **Database**: MS SQL
- **Authentication**: JSON Web Tokens (JWT)

## Features

### 🏢 Apartment Management
- **Apartment Operations**: Full CRUD functionality for apartments
- **Category System**: 
  - `AddCategory`: Create new apartment categories (e.g., Studio, Shared)
  - `DeleteCategory`: Remove unused categories
- **Facility Management**:
  - `AddFacility`: Add amenities (WiFi, Laundry, etc.)
  - `DeleteFacility`: Remove outdated facilities
- **Search & Discovery**:
  - `SearchForApartment`: Filter apartments by location/price
  - `ShowApartmentDetails`: View comprehensive apartment info
  - `GetApartment`: Retrieve specific apartment data
- **Lifecycle Management**:
  - `CreateApartmentProcess`: Step-by-step apartment listing creation
  - `UpdateApartment`: Modify existing listings
  - `DeleteApartment`: Remove apartment from platform

### 🔐 Authorization System
- Role-based access control for students/owners
- JWT authentication for all endpoints
- Secure credential management
- Session handling and token refresh

### 📅 Booking Management
- **Core Entities**:
  - `Apartment`: Primary listing unit
  - `Room`: Subdivision of apartments
  - `Bed`: Individual sleeping spaces
- **Booking Operations**:
  - `ApartmentBooking`: Complete reservation workflow
  - `AcceptBooking`: Owner approval process
  - `CancellBooking`: Reservation cancellation
- **User Features**:
  - `GetOwnerBookingRequests`: View pending/accepted bookings
  - `GetStudentBookingHistory`: Track past reservations
- **Common Utilities**: Shared booking logic and validations

### 💬 Comment Management
- `AddComment`: Post reviews/feedback on apartments
- `DeleteComment`: Remove inappropriate comments
- `GetComments`: View all comments for an apartment
- Moderation tools and spam detection
- Comment threading and replies

### ❤️ Favorite Management
- `AddFavoriteApartment`: Bookmark preferred listings
- `DelFavoriteApartment`: Remove from favorites
- `GetFavoriteAparts`: View saved apartments
- `ToggleFavorite`: Quick favorite/unfavorite toggle
- Personalized recommendation engine

### 👤 User Management
- **Owner Manager**:
  - Apartment listing analytics
  - Booking request dashboard
  - Revenue reports
- **Student Manager**:
  - Profile customization
  - Booking preferences
  - Notification settings
- **Common Features**:
  - Unified authentication flow
  - Profile management endpoints

### 🌱 Data Seeding
- `SeedingData`: Database initialization system
- Preloaded categories and facilities
- Sample apartments for demo purposes
- Test user accounts for all roles
- Consistent data reset capability

## Getting Started

### Prerequisites
- .NET 8
- Entity Framework Core, Cloudinary, Fluent Validation, Mapster
- MS SQL Server

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/hossamfc9/uniMate-Backend.git
   cd uniMate-Backend

   ```

3. Install Packages:
   ```bash
   # Core EF packages
   dotnet add package Microsoft.EntityFrameworkCore
   dotnet add package Microsoft.EntityFrameworkCore.Design
   dotnet add package Microsoft.EntityFrameworkCore.SqlServer
   dotnet add package Microsoft.EntityFrameworkCore.Tools

   # Authentication & Authorization
   dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer

   # Cloudinary integration
   dotnet add package CloudinaryDotNet

   # Validation
   dotnet add package FluentValidation.AspNetCore

   # Object mapping
   dotnet add package Mapster
   dotnet add package Mapster.DependencyInjection

   # Additional utilities
   dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
   dotnet add package Microsoft.AspNetCore.OpenApi
   dotnet add package Swashbuckle.AspNetCore
   ```

2. Configuration:
   ```
   appsettings.json
   {
      "MailSettings": {
         "Email": "your_mail@gmail.com",
         "DisplayName": "Uni_Mate Website",
         "Password": "your_password",
         "Host": "smtp.gmail.com",
         "Port": 587
      },
      "Jwt": {
         "Key": "your_secure_key_here",
         "Issuer": "UniMateBackend",
         "Audience": "UniMateUsers",
         "ExpiryInMinutes": 120
      },
      "Cloudinary": {
         "CloudName": "your_cloud_name",
         "ApiKey": "your_api_key",
         "ApiSecret": "your_api_secret"
      },
      "Logging": {
         "LogLevel": {
            "Default": "Information",
            "Microsoft.AspNetCore": "Warning"
         }
      }
   }
   ```