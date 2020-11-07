Message.ly is a user-to-user private messaging app using common patterns around authentication and authorization.


Setting up:
CREATE DATABASE messagely;
exit and then type
psql messagely < data.sql

npm install 
nodemon server.js


check to see all tables are in database: `\d`
check to see that there are some columns in the tables `\d messages`
add an env file and paste secret key : SECRET_KEY = abc123


