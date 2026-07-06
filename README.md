# Management of a Low-Cost Airline Company

This project is a complete application for the efficient management of operations within a low-cost airline company. The project was developed as a **university project** at the University of Bucharest, Faculty of Mathematics and Computer Science, Computer Science specialization, for the **Databases** course.

## Project Description
The main objective of this work is the organization and administration of the data structure specific to an airline company. The system enables detailed tracking of the aircraft fleet, flight routes, schedules, flight personnel (pilots and flight attendants), as well as customers, bookings made, and additional services purchased by them.

### Main Components and Modeling Rules:
- **Fleet and Maintenance:** Management of aircraft (registered with the `YR-` prefix) and the history of their technical interventions.
- **Infrastructure:** Allocation of aircraft to specific airports (identified by unique 3-letter IATA codes).
- **Flights and Routes:** Definition of air routes (distinct departure/arrival) and precise scheduling of flights (minimum duration of 20 minutes).
- **Crew:** Assignment of personnel (Pilots with ranks/flight hours and Flight Attendants with specific certifications) to flights, with clearly defined roles.
- **Customers and Bookings:** Management of passengers, issuing of unique tickets, and attachment of optional services (extra baggage, car rentals, priority boarding, etc.).

---

## Technologies Used

### Backend & Database:
- **Oracle Database 19c:** The relational database management system.
- **Node.js & JavaScript:** The runtime environment for the server and backend logic.
- **oracledb:** The official Oracle driver for Node.js, enabling real-time database querying.
- **DataGrip / Oracle SQL Developer:** Tools used for designing the conceptual schema and writing SQL scripts.

### Frontend:
- **HTML5 & CSS3:** Development of a responsive, modern graphical interface (dark theme / Dark Mode).

---

## Graphical Interface and Features
The application provides an interactive dashboard through which the user can perform:
1. **Secure Authentication:** A login window connected directly to the local Oracle database instance.
2. **Viewing and Sorting (Read):** Listing the system's tables with the option for dynamic sorting by column.
3. **DML Operations (Create, Update, Delete):** Editing cells directly from the interface and deleting records.
4. **Cascade Integrity:** Implementation of `ON DELETE CASCADE` constraints (for example, deleting a booking automatically removes the associated tickets and services).
5. **Reports, Statistics, and Complex Queries:** Automatic data extraction from multiple related tables, use of aggregate functions, the `HAVING` clause, and the use of compound and complex views (e.g., cost analysis per route, repair history for the previous year).

---

## Installation and Setup Guide

Follow the steps below to set up and run the project locally:

### 1. Database Configuration
Make sure you have **Oracle Database 19c** installed. Open your preferred tool (DataGrip or Oracle SQL Developer) and run the scripts from the documentation in the following order:
1. The table creation script (`10.1. Creating the tables`).
2. The data population script (`10.2. Inserting data into the tables`).

### 2. Initializing the Node.js Project
Open a terminal in the project's root directory and initialize the package manager to generate the `package.json` file:
```bash
npm init -y
```

### 3. Installing Required Dependencies
Install the official Oracle driver and the Express web framework by running a single command in the terminal:
```bash
npm install oracledb express
```

### 4. Starting the Application
Make sure the main server file (e.g., app.js or index.js) contains the correct connection credentials (user, password, connectString to the local instance, for example localhost:1521/orcl). Start the server by running:
```bash
node app.js
```