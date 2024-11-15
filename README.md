# Employee Management System (EMS)

## Overview

The **Employee Management System (EMS)** is a comprehensive application designed to manage employee-related information within an organization. It supports CRUD (Create, Read, Update, Delete) operations on employee data and includes several key modules such as employee management, Role assignments, and Leave request and Attendance.

The system follows best practices in software architecture, including the use of various design patterns such as Singleton, Factory, Strategy, and Repository. The application is built using .NET 8 for the backend and follows a layered architecture to separate concerns between different modules.

## Features

- **CRUD Operations for Employees**: Create, update, view, and delete employee details as well as leave request and attendance.
- **Pattern-Based Architecture**: Implements design patterns like Factory, Singleton, Strategy, Repository.
- **Database Management**: Includes migrations for schema updates.
- **Logging and Validation**: Integrated with validation services and custom logging mechanisms.

## Technology Stack

- **Backend**: .NET 8, C#
- **Database**: PostgreSQL Server (or any preferred database using EF Core)
- **Design Patterns**:
    - Factory Pattern
    - Singleton Pattern
    - Strategy Pattern
    - Unit of Work Pattern
    - Repository Pattern
- **Frameworks/Libraries**:
    - Entity Framework Core
    - AutoMapper for object-to-object mapping
    - FluentValidation for validation
- **Testing**: xUnit for unit testing, Moq for mocking dependencies
- **Logging**: NLog

## Project Structure
The project is organized into the following folders:

- **Controllers**: Contains controllers to handle API requests related to employees, attendance, leave requests, and authentication.
- **DAL (Data Access Layer)**: Contains the `ApplicationDbContext` class for database access using Entity Framework.
- **DTOs (Data Transfer Objects)**: Contains DTOs for attendance, employees, and leave requests to separate the domain models from the data sent over the wire.
- **Factory Pattern**: Implements the factory pattern for creating instances of leave requests.
- **Logs**: Contains log files generated by the application using NLog.
- **Migrations**: Contains Entity Framework migrations to manage database schema changes.
- **Models**: Defines the domain models for employees, attendance, leave requests, and roles.
- **Repository**: Implements repositories for handling database operations on the domain models using the Generic Repository pattern.
- **Services**: Contains the business logic for managing attendance, employees, and leave requests.
- **Strategy Pattern**: Implements different strategies for attendance tracking, such as daily and hourly tracking.
- **Unit of Work**: Implements the Unit of Work pattern to coordinate the work of multiple repositories.
- **Validator**: Contains classes for validating attendance, employee, and leave request data using FluentValidation.
- **Singleton**: Implements the singleton pattern to manage a single instance of classes that handle attendance tracking strategies.

## Technologies Used

- **ASP.NET Core**: Web framework used to build the application.
- **Entity Framework Core**: ORM for database operations.
- **FluentValidation**: Used for validating input data.
- **NLog**: Logging framework for logging errors and application events.
- **SQL Server**: Database used for storing employee, attendance, and leave data.
- **Repository Pattern**: Provides an abstraction over data access logic.
- **Unit of Work Pattern**: Ensures that multiple operations within a transaction either complete successfully or fail together.
- **Strategy Pattern**: Allows different attendance tracking strategies (daily, hourly) to be used based on business needs.

## Project Components

### 1. **Controllers**
- `AttendanceController`: Manages employee attendance requests.
- `AuthController`: Handles user authentication and registration.
- `EmployeeController`: Manages employee details.
- `LeaveRequestController`: Handles leave request submissions and approvals.

### 2. **DAL**
- `ApplicationDbContext`: Database context class for accessing and querying the database.

### 3. **DTOs**
- `AttendanceDTO`: Data Transfer Object for attendance-related operations.
- `EmployeeDTO`: Data Transfer Object for employee-related operations.
- `LeaveRequestDTO`: Data Transfer Object for leave request operations.

### 4. **Factory Pattern**
- `LeaveRequestFactory`: Factory class responsible for creating instances of leave requests.

### 5. **Models**
- `Attendance`: Represents employee attendance data.
- `Employee`: Represents employee information.
- `LeaveRequest`: Represents leave request data.
- `Role`: Represents roles assigned to users for role-based access control.

### 6. **Repository**
- `GenericRepository`: Generic repository for basic CRUD operations.
- `AttendanceRepository`: Repository for handling attendance data operations.
- `EmployeeRepository`: Repository for managing employee data.
- `LeaveRequestRepository`: Repository for leave request operations.
- `RoleRepository`: Repository for role management.

### 7. **Services**
- `AttendanceService`: Contains the business logic for handling attendance data.
- `EmployeeService`: Contains the business logic for managing employee information.
- `LeaveRequestService`: Contains the business logic for managing leave requests.

### 8. **Strategy Pattern**
- `DailyAttendanceTrackingStrategy`: Strategy for tracking daily attendance.
- `HourlyAttendanceTrackingStrategy`: Strategy for tracking attendance on an hourly basis.

### 9. **Unit of Work**
- `UnitOfWork`: Manages transactions and coordinates work between different repositories.

### 10. **Validators**
- `AttendanceValidator`: Validates attendance data.
- `EmployeeValidator`: Validates employee data.
- `LeaveRequestValidator`: Validates leave request data.

## Configuration

### 1. **AppSettings**
- `appsettings.json`: Contains application configuration settings, such as database connection strings and logging configurations.
- `nlog.config`: Configuration file for NLog to specify logging rules and targets.

### 2. **Dependency Injection**
- The services, repositories, and unit of work are registered for dependency injection in the `Program.cs` file.

## Getting Started

### Prerequisites
- .NET 6.0 or higher
- PostgreSQL Server

### Setting Up the Project
1. Clone the repository:
   ```bash
    git clone https://github.com/your-repo/EmployeeManagementSystem.git
2.Navigate to the project directory:
    cd EmployeeManagementSystem
3.Set up the database by Running Entity Framework migrations:
    dotnet ef database update
4.Run the application:
    dotnet run
### Logging
Logging is handled using NLog. The logs are configured in the log files, as defined in the nlog.config file.


