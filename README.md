# Event Services Management API

## Project Overview
This project is an Event Services Management API built with Node.js, Express, Azure SQL Database, REST, and GraphQL. The API manages clients, venues, and events. Events are the main resource and are connected to both clients and venues through database relationships.

The project demonstrates database integration, REST CRUD operations, GraphQL queries and mutations, pagination, error handling, and cloud deployment.

## Live Links
GitHub Repository: https://github.com/leslie1403/itmd544-api-dev 

Live REST API Base URL: https://itmd544-api-dev-fsfggsh6c6avfnes.westus2-01.azurewebsites.net/

Live GraphQL Endpoint: https://itmd544-api-dev-fsfggsh6c6avfnes.westus2-01.azurewebsites.net/graphql

## Technologies Used
- Node.js
- Express.js
- Azure SQL Database
- Microsoft SQL Server
- mssql
- GraphQL
- Apollo Server
- dotenv
- cors
- nodemon
- Postman
- Azure App Service

## Database Overview
The database uses three related tables:
 - clients
 - venues 
 - events

The events table connects to the clients and venues tables using foreign keys. Each event belongs to one client and one venue. One client can have many events, and one venue can host many events.

## REST API Endpoints
### General
- GET /
- GET /test-db

### Events
- GET /events
- GET /events?page=1&limit=2
- GET /events/:eventId
- POST /events
- PUT /events/:eventId
- DELETE /events/:eventId

### Clients
- GET /clients
- GET /clients/:clientId/events

### Venues
- GET /venues
- GET /venues/:venueId

### GraphQL Endpoint
GraphQL allows the user to request specific fields and retrieve related client and venue data in one request.
GraphQL is available at:

Local URL: http://localhost:3000/graphql

Live URL: https://itmd544-api-dev-fsfggsh6c6avfnes.westus2-01.azurewebsites.net/graphql

### Environment Variables
Create a .env file in the root of the project.

PORT=3000

DB_USER=your_database_username

DB_PASSWORD=your_database_password

DB_SERVER=your_server_name.database.windows.net

DB_NAME=your_database_name

The .env file should not be pushed to GitHub.

## Local Setup Instructions
1. Clone the repository using the link provided above
2. Move into the project folder.
3. cd itmd544-api-dev-assignment
4. Install dependencies.
5. npm install
6. Create the .env file using the environment variable example above. Start the development server.
7. npm run dev
8. Open the API locally: http://localhost:3000

## Testing Instructions

The REST API can be tested using a browser or Postman.
Recommended REST tests:

- GET /
- GET /test-db
- GET /events?page=1&limit=2
- GET /events/1
- POST /events
- PUT /events/:eventId
- DELETE /events/:eventId
- GET /clients
- GET /venues

The GraphQL API can be tested using Apollo GraphQL Sandbox at: http://localhost:3000/graphql

Recommended GraphQL tests:
- Query all events with nested client and venue data
- Create an event
- Update an event
- Delete an event
- Deployment Notes

The database is hosted on Azure SQL Database. The API is deployed using Azure App Service.

For deployment, the environment variables from the .env file must be added to the Azure App Service configuration settings. The deployed application provides both REST API routes and the GraphQL endpoint.

## Error Handling

The API includes basic error handling for:
- Missing required event fields
- Invalid pagination values
- Event not found
- Venue not found
- Database/server errors


## Completed features:
- Azure SQL Database connection
- REST API endpoints
- Event CRUD operations
- Client and venue GET routes
- GraphQL endpoint
- GraphQL queries and mutations
- Nested GraphQL client and venue data
- Pagination for events
- Clean date and time formatting
- Basic error handling
- Azure deployment