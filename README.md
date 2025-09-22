# ICS2609_Lab4 - Extending Authentication API with SQL JOIN Reports

## Project Overview
In this project, we extend the Lab 3 Authentication API by adding new database tables and implementing SQL JOIN-based reports. All new report endpoints are JWT-protected and tested using Postman.

## JOIN Explanations
A) INNER JOIN - In this query, it uses inner join to connect the users table with user_roles and roles, so each user is shown with their assigned role. The result only displays records where a user has a matching role.

B) LEFT JOIN - This query uses left join to show all users from the users table, even if they don’t have a matching profile in the profiles table. If no profile exists, the profile fields (phone, city, country) appear as NULL.

C) RIGHT JOIN - A right join returns all rows from the table on the right side of the join, even if there’s no matching record in the left table. In this query, it ensures all roles from the roles table are listed, even if no user is assigned to them.

D) FULL OUTER JOIN (emulated) - A full outer join returns all records from both tables, showing matches where they exist and NULL where they don’t. In this query, it’s emulated with left join union right join so both users without profiles and profiles without users are included.

E) CROSS JOIN - In this query, it uses a cross join that combines every row from the first table with every row from the second table, creating all possible pairs. In this query, each user will be matched with every role, even if they don’t actually have that role.

F) SELF JOIN - In this query, the users table is joined twice so we can show which user referred another user along with their emails.

G) Latest login per user - This query uses a left join with a subquery that finds each user’s most recent login. It shows all users, and if a user has no logins, their login details (ip_address, occurred_at) appear as NULL.

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

## Endpoints
1. Authentication
- POST /auth/signup → Register a new user
- POST /auth/login → Login and receive JWT token
- POST /auth/logout → Logout (JWT required)
- GET /auth/profile → Get user profile (JWT required)
