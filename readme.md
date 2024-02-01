# userSystem

**Introduction:**
Welcome to the userSystem Panel! This comprehensive system is designed to streamline user management with a user-friendly interface. Below, you'll find a brief overview of the features available to users and administrators.

**Live Project Link 🔥🔥**
 - [Project link](https://admino.onrender.com/)

# Table of Contents
- [Features](#features)
- [Endpoint](#endpoints)
- [Libraries](#libraries)
- [Download  Postman Api Folder](#downloads)
- [Preview Images](#preview)
- [Run Website](#getting-started)
- [About](#about)


## Features:

### For Users:

1. **User Registration:**
   - Users can register with the system, providing necessary information to create their profiles.

2. **Profile Management:**
   - View and update personal profile details.

3. **Image Storage:**
   - Easily store and manage profile images.

4. **Password Recovery:**
   - In case a user forgets their password, an email will be sent with a password reset link.

### For Administrators:

1. **User Management:**
   - Activate or deactivate users.
   - Promote users to admin or demote them to normal user status.
   - View a comprehensive list of all users in the system.

2. **Profile Administration:**
   - Update user details.
   - Delete user accounts as needed.

3. **Image Storage:**
   - Efficiently store and manage user images.

4. **Security Measures:**
   - Authentication using Cookies and JWT for secure access.

5. **Password Recovery Workflow:**
   - Users can initiate a password recovery process through a reset link sent via email.
   - Password reset links expire within 1 hour for enhanced security.


## Endpoints

### User Authentication
- **Register user:**
  - Endpoint: `POST /api/v1/auth/register`
  - Description: register user details.
  ```javascript
  const link="http://localhost:3000/api/v1/auth/register"
  const body:{"name":"Suhail","email":"spdiy12k@gmail.com","password":"aB345678","profileImg":file}
  ```

- **Login user:**
  - Endpoint: `POST /api/v1/auth/login`
  - Description: user has to login using email and password
  ```javascript
  const link="http://localhost:3000/api/v1/auth/login"
  const body:{"email":"spdiy12k@gmail.com","password":"aB345678"}
  ```

- **Forget user Password:**
  - Endpoint: `POST /api/v1/auth/forget-password`
  - Description: forget password by email. user has to verify his email. then link will send to the user's email
  ```javascript
  const link="http://localhost:3000/api/v1/auth/forget-password"
  const body: {"email":"spidy12k@gmail.com"}
  ```

- **change user Password:**
  - Endpoint: `POST /api/v1/auth/change-user-password`
  - Description:  change user password.
  ```javascript
  const link="http://localhost:3000/api/v1/auth/change-user-password/65baacdd2938ca0c674b1848"
  //password will contains at least 8 min char and 15 max character
  //passwill should contains upper,lower,numeric character
  const body={
        "password": "q1A4383",
        "token":"token"
        }
  ```

- **logout user:**
  - Endpoint: `POST /api/v1/auth/logout`
  - Description: all session will remove releated to user.
  ```javascript
  const link="http://localhost:3000/api/v1/auth/logout"
  ```

### user Details

- **Get All Users:**
  - Endpoint: `GET /api/v1/user/all`
  - Description: Retrieve information about all users.only admin can see all users.
  ```javascript
  const link="http://localhost:3000/api/v1/user/all"
  ```

- **Get User by Id:**
  - Endpoint: `GET /api/v1/user/:id`
  - Description: Retrieve information about a specific user.
  ```javascript
   const link="http://localhost:3000/api/v1/user/65bbba1914df314335a96a19"
  ```

- **Update Usr by Id:**
  - Endpoint: `PUT /api/v1/user/update/:id`
  - Description:  Update specific user details. user can update his name and profileimg
  - Additional: Admin can change user type and change active and inactive status
  ```javascript
   const link="http://localhost:3000/api/v1/user/update/65bbba1914df314335a96a19"
   //one of these fields can be updated
   const body={"name":"vasu", "profileImg":file,"imgLink":"old img name"}
  ```

- **Delete User by Id:**
  - Endpoint: `DELETE /api/v1/user/delete/:id`
  - Description:  Delete a specific user. only admin can delete user
  ```javascript
   const link="http://localhost:3000/api/v1/user/delete/65bbba1914df314335a96a19013"
  ```

### Image
- **Get Image By Name**
  - Endpoint: `GET /api/v1/image/:imgLink`
  - Description:  Retrieve a specific image using imgLink.
  ```javascript
  //bydefault i'm storing image in db without any 3rd party library
   const link="http://localhost:3000/api/v1/image/1706801837422.jpeg"
  ```

## Libraries 

- [mongoose](https://www.npmjs.com/package/mongoose)
  - Purpose: Used for interacting with the database
- [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)
  - Purpose: Used for authentication
- [multer](https://www.npmjs.com/package/multer)
  - Purpose: Used for handling image uploads.
- [nodemailer](https://www.npmjs.com/package/nodemailer)
  - Purpose: Used for sending emails.




## Downloads
   **Important**

    Desscription: Add this into .env file

   ```javascript
         nodeMailerkey=nodemailer key
         USER_EMAIL=your email Id
         mongo=your mongoDb Url
         forgot_Link=http://localhost:3000
         link=http://localhost:3000
   ```
      
      
      
   **Postman Api's Folder**
   - folder link => [postman Api endPoints](https://github.com/itsmeAryan/userSystem/tree/master/postmanApiFolder)
   
   ```bash
   # Open Postman
   # Select the "Import" option
   # Choose the file path of the Postman API collection

   ```
  ## Preview
  ***Server Images***
  ![Screenshot from 2024-02-02 03-59-20](https://github.com/itsmeAryan/userSystem/assets/85377449/35d2027e-f307-42d1-b8f7-92c5156daa6b)
![Screenshot from 2024-02-02 03-58-51](https://github.com/itsmeAryan/userSystem/assets/85377449/308c8c97-eb95-496a-acb0-266b4a268809)
![Screenshot from 2024-02-02 03-58-56](https://github.com/itsmeAryan/userSystem/assets/85377449/feb508e9-e6d5-411a-ae19-4ab1aeff5335)
![Screenshot from 2024-02-02 03-59-00](https://github.com/itsmeAryan/userSystem/assets/85377449/d6709d01-b5bf-4947-a9f0-36196f1b634c)
![Screenshot from 2024-02-02 04-13-13](https://github.com/itsmeAryan/userSystem/assets/85377449/3876fc30-966c-49a6-a6f2-c8f3c6d57fe1)
![Screenshot from 2024-02-02 04-13-19](https://github.com/itsmeAryan/userSystem/assets/85377449/c084b23d-8cfd-4f12-a598-9d3e3944c251)


## Getting Started:

1. Clone the repository.
2. Install dependencies with `npm install`.
3. Set up MongoDB and configure the database connection.
4. Run the application using `npm start`.
5. Access the admin panel via the provided URL.

**Note:** As soon as the server is started, you can also access the frontend website by navigating to the following URL in your browser:

```javascript
   http://localhost:3000/

```
## About
**Created By:** Mr Suhail
- Email address letxandy@gmail.com
