Prompt 1: Bootstrap Project
Create a monorepo project using GitHub with a React FE and Spring Boot BE. Configure TypeScript, ESLint, Prettier, Husky, Liquibase, PostgreSQL etc. Create folders for common, frontend, and backend. Initialize a shared types package.
 
Prompt 2: Authentication System
Implement user authentication using JWT. Create an Express middleware to issue access tokens on login. Secure endpoints using token verification middleware. On the frontend, build a login form that submits credentials and stores the token in localStorage. Show a logged-in UI state if a valid token exists. Write unit tests for the login service and auth middleware.
 
Prompt 3: Role-Based Access Control
Enhance the backend to enforce Admin and Officer roles. Implement middleware to restrict API access. Frontend should conditionally render UI elements based on user role. Write integration tests for role logic.
 
Prompt 4: Manual Data Entry Form
Build a form with two input fields: Driver ID and Vehicle Reg. Submit button should be enabled when either field is filled. Add client-side validation and display server-side error responses. Backend should return mock data for now.
 
Prompt 5: Lookup Results
Create API to return outstanding WoAs and Notices. Return hardcoded JSON objects (to be replaced with DB calls later). Frontend should display separate tables for driver-linked and vehicle-linked entries. Include Jest tests.
 
Prompt 6: Action Buttons & Persistence
Add buttons to mark entries as "Executed" or "Paid". Require authentication and role check. Backend should persist actions to a database and log them with timestamp and user ID. Audit log table should be created.
 
Prompt 7: PDF Generation
On action, generate a server-side PDF with entry details, user ID, timestamp, and a unique reference. Return as a downloadable blob to frontend. Frontend should provide a preview and download option. Test with sample data.
 
Prompt 8: XML Export Job
Create a backend cron or trigger endpoint to generate an XML file daily. Include all executed/paid transactions for that day with timestamp and user ID. Allow download from admin panel. Include schema validation.
 
Prompt 9: Reconciliation Module
Build admin interface to upload TRAFMAN XML file. Parse and compare with internal records. Display mismatches and allow tagging with resolution comments. Store resolution metadata. Write integration tests.
 
Prompt 10: Officer Session History
Track all lookup and action events by a logged-in officer per session. Store in memory or local storage. Display a table showing past inputs, timestamps, and statuses. Clear session on logout.
 
Prompt 11: Final Integration
Wire all modules together. Test workflows end-to-end. Validate permission boundaries. Run full test suite. Ensure all routes are secured, logs are persisted, and PDFs/XML are generated correctly.