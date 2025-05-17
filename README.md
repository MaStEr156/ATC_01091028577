# Event Booking System

A full-stack event booking system built with ASP.NET Core 8.0 and React. This system allows users to browse, book, and manage events, with an admin interface for event management.

## Prerequisites

Before you begin, ensure you have the following installed:
- .NET 8.0 SDK
- Node.js (v18 or higher)
- npm (v9 or higher)
- SQL Server (Express or Developer edition)
- Git
- Visual Studio 2022 or Visual Studio Code with C# extensions

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/MaStEr156/ATC_01091028577.git
cd Event-Booking-System
```

### 2. Backend Setup (API)

1. Navigate to the API project:
```bash
cd Event-Booking-System-API
```

2. Install Entity Framework Core tools (if not already installed):
```bash
dotnet tool install --global dotnet-ef
```

3. Apply database migrations:
```bash
dotnet ef database update
```

4. Start the API:
```bash
dotnet run
```

The API will be available at `https://localhost:7054`
and to open Swagger UI: `https://localhost:7054/swagger`

### 3. Frontend Setup

1. Open a new terminal and navigate to the frontend project:
```bash
cd Event-Booking-System-Frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory with the following content:
```env
VITE_API_URL=https://localhost:7054
```

4. Start the development server:
```bash
npm run dev
```

The frontend application will be available at `http://localhost:5174`

## Project Structure

### Backend (API)
```
Event-Booking-System-API/
├── Controllers/           # API endpoints
├── EventService/         # Business logic and DTOs
├── DB-Layer/            # Database context and entities
│   ├── Entities/        # Entity models
│   └── Persistence/     # DbContext and configurations
└── Program.cs           # Application entry point
```

### Frontend
```
Event-Booking-System-Frontend/
├── src/
│   ├── components/     # Reusable UI components
│   ├── context/       # React context providers
│   ├── pages/         # Page components
│   ├── services/      # API service functions
│   ├── types/         # TypeScript type definitions
│   └── utils/         # Utility functions
```

## Features

### Backend
- JWT Authentication
- Role-based authorization
- Entity Framework Core with SQL Server
- Repository pattern
- Unit of Work pattern
- Soft delete functionality
- CORS configuration
- Swagger documentation

### Frontend
- User authentication (login/register)
- Event browsing and searching
- Event booking management
- Admin dashboard for event management
- Category management
- Responsive design

## API Endpoints

### Authentication
- POST `/api/Auth/Register` - Register a new user
- POST `/api/Auth/Login` - Login user
- POST `/api/Auth/RefreshToken` - Refresh JWT token
- POST `/api/Auth/Update-Profile` - Update User Profile
- POST `/api/Auth/Assign-Role` - Assign role to a user
- POST `/api/Auth/Deassign-Role` - Deassign user a role
- GET `/api/Auth/Get-User` - Gets User information
- POST `/api/Auth/Logout` - Logs out User

### Events
- GET `/api/Event/GetAllEvents` - Get all events
- GET `/api/Event/GetEventById/{id}` - Get event by ID
- POST `/api/Event/CreateEvent` - Create new event
- PUT `/api/Event/UpdateEvent` - Update event
- DELETE `/api/Event/DeleteEvent/{id}` - Delete event
- POST `/api/Event/SoftDeleteEvent/{id}` - Soft delete event

### Categories
- GET `/api/Category/GetAllCategories` - Get all categories
- POST `/api/Category/CreateCategory` - Create new category
- PUT `/api/Category/UpdateCategory` - Update category
- DELETE `/api/Category/DeleteCategory/{id}` - Delete category
- POST `/api/Category/SoftDeleteCategory/{id}` - Soft delete category

### Bookings
- GET `/api/Booking/GetUserBookings` - Get user's bookings
- POST `/api/Booking/CreateBooking` - Create new booking
- DELETE `/api/Booking/CancelBooking/{id}` - Cancel booking

## Technologies Used

### Backend
- ASP.NET Core 8.0
- Entity Framework Core
- SQL Server
- JWT Authentication
- AutoMapper
- Swagger/OpenAPI

### Frontend
- React 18
- TypeScript
- Tailwind CSS
- React Router
- Axios
- React Query
- Vite

## Development

### Backend Development
1. Create a new branch for your feature
2. Make your changes
3. Add migrations if needed:
```bash
dotnet ef migrations add YourMigrationName
dotnet ef database update
```
4. Submit a pull request

### Frontend Development
1. Create a new branch for your feature
2. Make your changes
3. Submit a pull request

## Browser Support

The frontend application is tested and supported on:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## License

This project is licensed under the MIT License. 
