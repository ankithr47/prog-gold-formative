# Cricket Club Management Application
Domain: Sports Club Management  
Description:
This aims to be a dynamic web application made for Norton Cricket Club to manage cricket net bookings. Some key features are:
- **Managing users**
  - User register and log in
  - Each user's account has name, email, and role (member/admin)
- **Booking time slots**
  - Users can see availability of net slots for given dates and times
  - Authenticated users can book a time slot & provide a description for their session. The time slot is updated from available to booked with session description underneath
  - Admins can modify slots as needed
- **Real-time slot management**
  - system tracks slot availability in real time
  - Users can book available slots, and can't book unavailable slots

## Entities
there are 2 main entities:

**Users (people)**:
  - key features:
    - id: unique user ID
    - email: email address
    - name: full name of user
    - role(member/admin)
    - password
    

**Booking net slots (Events)**:
  - key features:
    - date: slot date
    - time: slot time
    - slot_id: unique ID for slot
    - user_id: ID of user who booked slot(if booked)
    - description: description of the session being booked
    - status: whether slot available or not
   
## GET and POST Methods
**Users**:
- GET /users
  - returns list of all names and user IDs
- GET /users/:id
  - returns details of a user by ID, ie bookings made
- POST /users
  - to register a new user, requiring name, email, and password in request body
- POST /users/login
  - to authenticate a user (ie log them in), requiring email and password in request body
- POST /users/:id/update
  - Makes user able to update their profile information (ie update name, password, email), requiring email, password, name in request bodh

**Booking net slots**:
- GET /slots
  - list of all slots and their IDs, statuses, times, dates
- GET /slots/:id
  - returns details of a specific slot by id, ie who booked it, when it was booked
- POST /slots
  - to book a currently available slot, requiring description(of the session), date, time, user_id in request body
- POST /slots/:id/book
  - Updates slot status to booked, requiring user_id in request body


  
  

