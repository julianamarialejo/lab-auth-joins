# ICS2609_Lab4 - Extending Authentication API with SQL JOIN Reports

## Project Overview
In this project, we extend the Lab 3 Authentication API by adding new database tables and implementing SQL JOIN-based reports. All new report endpoints are JWT-protected and tested using Postman.

##  Setup Steps/How to Run
1. Download this repository
> https://github.com/julianamarialejo/lab-auth-joins

2. Install dependencies
> npm install

3. Configure .env with database + JWT secret and set up environment variables
> Copy .env.example to .env

4. Run the server
> npm run dev

5. API will be running at:
> http://localhost:3000

6. Test the health with browser
> http://localhost:3000/api/health

##Endpoints
1. Authentication
- POST /auth/signup → Register a new user
- POST /auth/login → Login and receive JWT token
- POST /auth/logout → Logout (JWT required)
- GET /auth/profile → Get user profile (JWT required)
