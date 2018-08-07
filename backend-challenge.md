# Mimo Backend Coding Challenge

Your objective is to create a basic version of the Mimo server functionality.

The point of this exercise is not to create a fully-functional bug-free server implementation,
but rather to look how you would design such a server system and how you approach different problems.

Write the server with ASP.NET Core, backed by Entity Framework Core with SQLite as database 
(so we don't have to setup a full blown database).

The server should expose only REST endpoints using JSON as the format.

## Data structure

### Courses

- There are multiple **courses** (create a "Swift", "Javascript" and "C#" course in the database)
- Each **course** has multiple **chapters**
- **Chapters** have a specific order in which they are displayed
- Each **chapter** has multiple **lessons**
- **Lessons** have a specific order in which they are displayed

### Users

- There are multiple **users** accessing the REST endpoints (e.g., from the Mimo app)
- You don't have to create an authentication system, just hardcode any user-specific actions to a single user
- Each user can solve multiple **lessons**
- Each **lesson** can be solved multiple times
- Track the time the **user** starts the **lessons** and the time the **user** completes the **lesson**

### Achievements

- There are **achievements** for completing different objectives (see below)
- Each **user** can complete each of the achievements below
- Once a user completes an **achievement**, mark it as completed

#### Objectives

- Complete 5 lessons
- Complete 25 lessons
- Complete 50 lessons
- Complete 1 chapter
- Complete 5 chapters
- Complete the Swift course
- Complete the Javascript course
- Complete the C# course

## API

### Lesson progress

Create an endpoint where the Mimo app can send information about lessons that the user completed to.
The app will send the following data:
- Which lesson was completed
- When was the lesson started
- When was the lesson completed

### Achievements

Create an endpoint where the Mimo app can request which achievements the users has completed
The app needs the following data:
- An identifier for the achievement
- If the achievement is completed or not
- What the progress of the achievement is (e.g. if the user solved three lessons, 
  it should return "3" for the lesson completion achievements)
