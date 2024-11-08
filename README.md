# HotelManagement

HotelManagement is a hotel booking application designed to streamline hotel reservations. This project consists of a **WPF application** for the front end and a **.NET Core API web application** for the backend, handling room management, booking, and payments.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies](#technologies)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Database Schema](#database-schema)
- [Endpoints](#endpoints)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Overview

HotelManagement provides a platform for managing hotel bookings, including room availability, checkouts, payments, and reservations. The WPF application offers a user-friendly interface for hotel staff, while the .NET Core API handles data management and business logic.

## Features

- Room Management: Display available rooms with filters, add and remove rooms.
- Booking Management: Handle check-in, check-out, and reservation processes.
- Payment Processing: Integrates with payment gateways to manage payments.
- Search and Filtering: Search for available rooms with specified criteria.
- User Interface: Easy-to-navigate WPF interface with essential functionalities.

## Technologies

- **Frontend**: WPF (.NET)
- **Backend**: .NET Core API
- **Database**: SQL Server
- **Payment Integration**: VNPAY

## Architecture

The application uses a client-server architecture with a separate WPF front-end and .NET Core API back-end. The API is responsible for managing requests, performing CRUD operations, and integrating with external services (like payment processing).

## Getting Started

### Prerequisites

- [.NET SDK 8.0](https://dotnet.microsoft.com/download)
- [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
- [Visual Studio](https://visualstudio.microsoft.com/) (for WPF and .NET Core development)
- VNPAY Account (for payment integration)

### Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/HotelManagement.git
    cd HotelManagement
    ```

2. **Set up the Database**:
   - Restore the database schema provided in `/Database/FUMiniHotelManagement.sql`.

3. **Configure the API**:
   - Update the database connection string in `appsettings.json` for the .NET Core API project.
   - Set up VNPAY credentials in `appsettings.json` under the Payment section.

4. **Build the Solution**:
   - Open the solution in Visual Studio and build it.

### Running the Application

1. **Start the API**:
   - Navigate to the .NET Core API project and run:
     ```bash
     dotnet run
     ```

2. **Run the WPF Application**:
   - In Visual Studio, set the WPF project as the startup project and run it.

## Database Schema

The database structure is centered around the booking and payment system with the following tables:

- **Rooms**: Stores room details.
- **BookingReservation**: Tracks each reservation.
- **Payments**: Contains payment information, with fields for payment time, status, and a one-to-one relationship with BookingReservation.
- **Users**: Stores information about users, including roles.

> Refer to `Database/FUMiniHotelManagement.sql` for the complete database schema.

## Endpoints

The API exposes various endpoints for managing the hotel operations:

- **Rooms**:
  - `GET /api/rooms` - Get all available rooms.
  - `POST /api/rooms` - Add a new room.
  - `PUT /api/rooms/{id}` - Update room details.
  - `DELETE /api/rooms/{id}` - Remove a room.

- **Bookings**:
  - `POST /api/bookings` - Create a new booking.
  - `GET /api/bookings/{id}` - Get booking details.
  - `PUT /api/bookings/{id}` - Update booking details.

- **Payments**:
  - `POST /api/payments` - Process a new payment.
  - `GET /api/payments/{id}` - Get payment status.

## Usage

### Booking a Room

1. Search for available rooms using the search bar in the WPF application.
2. Select a room and proceed with the booking process.
3. Confirm the reservation and make a payment if required.

### Checking Out

1. Go to the Bookings section.
2. Select the booking to check out.
3. Confirm the checkout and finalize the payment.

## Contributing

We welcome contributions to improve HotelManagement. To contribute:

1. Fork the repository.
2. Create a new branch:
    ```bash
    git checkout -b feature/YourFeature
    ```
3. Commit your changes:
    ```bash
    git commit -m 'Add your feature'
    ```
4. Push to the branch:
    ```bash
    git push origin feature/YourFeature
    ```
5. Open a Pull Request.

## License

This project is licensed under the MIT License.

---

> Note: For any questions, feel free to contact the project owner.
