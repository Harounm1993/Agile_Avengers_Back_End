# Agile Avengers - Holistic Tracking App

- **Our Problem**: Bootcampers are disengaged with the current holistic documentation experience because google forms are not engaging, bootcampers don’t understand the value of documenting their SoC experience, or what happens to their reflections with no access to it when it’s sent.

- **Solution**: A storyboard where bootcampers can record their experiences and how they are feeling in a fun and engaging way. Bootcampers will be able to view their posts allowing them to be reflective, monitor their moods and celebrate their achievements. This will be a mobile app - PWA - bootcampers can use their phones rather than their laptop.

---

# Set-up

1. Clone the repo from https://github.com/SchoolOfCode/back-end-final-project-agileavengers.git

2. Install any node modules: **npm install**

3. Run using: **npm run start**

4. OPTIONAL - Drop all current tables, create new tables and populate them with the seed data using: **npm run reinitialiseTables**

# GET Requests

### GET the homepage

**http://localhost:3000/**

### GET all posts for all users

**http://localhost:3000/posts**

### GET all posts for a user with user_id

**http://localhost:3000/posts/userId**

### GET a post by it's individual post id

**http://localhost:3000/posts/id**

### GET all favourited posts from a user with user_id

**http://localhost:3000/posts/userId/fave**

### GET all moods for all users

**http://localhost:3000/moods**

### GET all moods for a specific user with user_id

**http://localhost:3000/moods/userId**

### GET all trophies for a specific user with user_id

**http://localhost:3000/trophies/userId**

### GET all awarded trophies for a specific user with user_id

**http://localhost:3000/trophies/userId/awarded**

---

# POST Requests

### POST a new post:

**http://localhost:3000/posts**

user_id autogenerated when logged in and date will be auto set to current date with the format of YYYY-MM-DD.

{  
user_id (number),  
 post (sting),  
 multimedia (string),  
 date (date),  
 favorite (boolean)  
}

### POST a new mood:

**http://localhost:3000/moods**

Date is auto set to current date with format YYYY-MM-DD so there is no need to enter a date when sending the post request.

{  
user_id (number),  
mood (number),  
date (date)  
}

### POST a new user:

**http://localhost:3000/users**

Date is NOT auto set in this instance, you need to input the course's start date with format YYYY-MM-DD.

Personality type is your Myers-Briggs personality type in the format INTP.

{  
name (string),  
email (string),  
password (string),  
personality (string),  
start_date (date),  
points (integer)  
}

---

# PATCH Requests

Use these requests for updating users or posts information.

### PATCH an existing post

**http://localhost:3000/posts/postId**

All parameters are not required, only include those that need updating. Request body is in the format of:

{  
name (string),  
email (string),  
password (string),  
personality (string),  
start_date (date),  
points (integer)  
}

### PATCH an existing user

**http://localhost:3000/users/userId**

All parameters are not required, only include those that need updating. Request body is in the format of:

{  
user_id (number),  
post (sting),  
multimedia (string),  
date (date),  
favorite (boolean)  
}

---

# DELETE Requests

### DELETE a post - Using the PostID we can delete each individual post and remove it from the database.

**http://localhost:3000/posts/postId**
