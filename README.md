### Message.ly 
This is a user-to-user private messaging app using common patterns around authentication and authorization.

### Setting up:
1. On the terminal type psql and then `CREATE DATABASE messagely;`
2. Exit and then type `psql messagely < data.sql` to import the tables
3. Add an env file and paste secret key : SECRET_KEY = abc123
4. Run `npm install` 
5. Run `nodemon server.js`
6. To run tests:  
  a. psql   
  b. `createdb messagely_test`  
  c. \c messagely_test  
  d. \i data.sql  
  e.`npm run tests`
  (`jest -i` the -i parameter so the tests run in band, so there are no conflicts between asynchronous tests which communicate with the database (if they were to run at the same time) - https://jestjs.io/docs/en/cli#--runinband )

Some useful commands: 

* check to see all tables are in database: `\d`
* check to see that there are some columns in the tables `\d messages`

To check the different routes on insomnia, refer to the tests that show how it should look like. Here is one example: 

POST http://localhost:3000/auth/register

With this input:
```json
{
"username": "test2",
"password": "test",
"first_name": "Test",
"last_name": "Testerson",
"phone": "555-555-5555"
}
```
As an output you should get a token that shows the server has been authenticated
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3QyIiwiaWF0IjoxNjA0ODEwMjY5fQ.U9ocxRLWLcVwOkN7rTp7TRvPtq0ihTlwb6_v02pLvRk"
}
```
