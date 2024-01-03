# InstaShow
Online Movie Ticket Booking App


Overview:

InstaShow is a dynamic web application that for movie ticket booking, built using Vue JavaScript, 
HTML and Jijnja2 templates with Bootstrap CSS for Frontend, SQLite for database and Flask Python 
for Backend. Redis used for caching, and batch jobs done using celery, Redis. YAML to document use 
of Flask Restful API, CRUD operations. Run on WSL in windows. The application is designed as a 
multi-user platform, with at least one required admin and additional users. Its primary function 
revolves around booking show tickets, allowing users to reserve tickets for numerous movies. The 
administrative capabilities empower the admin to create and manage theatres and shows. Each 
theatre is defined by essential attributes such as ID, name, location, and capacity, while each show is 
characterized by its own set of parameters, including ID, name, rating, tags, and ticket prices. The 
flexibility of the system permits theatres to host multiple shows concurrently, and it automatically 
displays the most recently added shows for user convenience. This app also incorporates dynamic 
pricing based on availability of show tickets and time left for the show. 



Models:

User model (with password hashing for security), Theatre model (location, capacity, customers, 
revenue), Book tickets model (with booking details – shows and theatres), Show model (with details 
of each of the movie shows), tag model (with different movie tags), running model (with details of 
running shows at times when user is logged in), messages model(with details of messages and alerts 
sent to the user upon cancellations or errors) and show tags model(to connect between shows and 
their tags). 



System Design and Key Features:

The application adheres to a modular design approach, prioritizing the separation of concerns and 
ease of maintenance. Below is an overview of its key components:

▪ Vue instances defined in JavaScript files are responsible for dynamically rendering content. 
Crafted using Jinja2 and Bootstrap CSS, they are categorized by distinct views

▪ Routes: Routes define the URL endpoints that correspond to various functionalities. They 
manage user requests, interact with the models, and facilitate the rendering of the 
appropriate templates.

▪ User Authentication: The application offers user registration, login, and admin login features. 
User passwords undergo secure hashing before storage for enhanced security. Admin login 
using RBAC, User signup.

▪ Admins can manage theatres, tags and shows. Search functionality implemented for shows, 
theatres based on location, tag, rating, name, etc. 

▪ Backend jobs include user triggered async export jobs like export CSV of shows or theatres 
possible for users, export theatre or show details in MS Word document, reporting jobs daily, 
monthly and alert jobs notifications for errors or cancellations.

▪ Form for username and password (both login and signup), Flask Security or JWT based Token 
Based Authentication only

▪ Add an admin user whenever a new database is created

▪ Theatre management – add, edit, remove (varied pricing and experience for each theatre)
Show management – add, edit, remove, add screening or allocate theatres
Tags management – add, edit, remove

• List the shows available for a given timeframe to the users, Ability to book multiple tickets 
for a show at a given theatre, Ability to stop taking bookings in case of a houseful.

• If user hasn’t visited or booked anything on a day, daily reminders sent using celery batch 
jobs in backend.

• The monthly entertainment review report sent, consist of bookings made by a user in a given 
month, shows seen, ratings for the shows etc. On the first day of the month - Start a job, 
Create a report, Send it as email

• Redis used for caching with expiry, Flask-Restful API CRUD operations, YAML Documentation

• Additional features: Dynamic pricing, well designed templates for export jobs backend



Conclusion:

In summary, the InstaShow, Movie Ticket Booking app MAD 2 project exemplifies a meticulously 
designed and feature-enriched web application constructed on the Vue JavaScript, CSS, HTML, and 
Flask framework. With its modular architecture, robust user authentication, streamlined show and 
theatre management, smooth booking experience, async reminders and promotions, and powerful 
search functionality, the application delivers a user-friendly and well-organized platform for online 
ticket booking. Furthermore, the integration of Flask extensions enhances form handling and URL 
routing, further enhancing its robust and user-focused design
