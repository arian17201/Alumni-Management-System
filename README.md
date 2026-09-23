# Alumni Management System

A PHP and MySQL-based **Alumni Management System** designed to help an educational institution connect with its alumni, manage alumni activities, publish opportunities, and maintain communication between alumni, students, and administrators.

## 📌 Project Overview

The **Alumni Management System** provides separate functionality for **Alumni** and **Administrators**.

Alumni can register and log in to the portal, view events and gallery content, share achievements, post job opportunities, send queries, and volunteer as mentors.

Administrators can log in to an admin panel to manage events and review alumni-submitted information such as queries, achievements, job postings, and mentor requests.

## ✨ Features

### 👨‍🎓 Alumni Features

- Alumni registration and login
- Alumni profile information including:
  - Name
  - Email
  - Department
  - Batch
- Alumni portal/dashboard
- View upcoming alumni events
- View gallery images
- Send queries to the administration
- Post job opportunities for other alumni/students
- Share professional or academic achievements with supporting files
- Submit requests to become a mentor
- Logout functionality

### 🛠️ Administrator Features

- Secure admin login/session handling
- Admin dashboard
- View received alumni queries
- View submitted alumni achievements
- View posted job opportunities
- View mentor requests
- Add new alumni events
- Delete existing events
- Upload event images/files
- Export job-posting information to an Excel file

### 🖼️ Media Management

The project includes image/file upload functionality for:

- Alumni achievements
- Event information
- Gallery content

Uploaded files are stored in the project directories and relevant information is stored in MySQL.

## 🧰 Technologies Used

| Technology | Purpose |
|---|---|
| **PHP** | Backend/server-side application logic |
| **MySQL / MariaDB** | Database management |
| **HTML5** | Web page structure |
| **CSS3** | User interface styling |
| **JavaScript** | Client-side functionality |
| **phpMyAdmin** | Database import/management |
| **table2excel.js** | Exporting table data to Excel |

## 📂 Project Structure

```text
Alumni-Management-System/
│
├── aboutus.php
├── achievements.php
├── adminhome.php
├── adminlogin.php
├── alumnihome.php
├── alumnilogin.php
├── alm.sql
├── beamentor.php
├── dbconnect.php
├── display_images.php
├── events.php
├── gallery.php
├── logout.php
├── mentorrequests.php
├── navbaradmin.php
├── navbarindex.php
├── navigationbar.php
├── postajob.php
├── postedjobs.php
├── queries.php
├── redirectpostsignup.php
├── scrolltotop.php
├── sendquery.php
├── shareachievements.php
├── signup.php
├── updateevents.php
├── userexists.php
│
├── assets/
│   ├── css/
│   │   ├── stylehome.css
│   │   └── stylesheetalumni.css
│   │
│   ├── images/
│   │   └── ...
│   │
│   └── js/
│       └── table2excel.js
│
├── events/
│   └── ...
│
└── uploads/
    └── ...
```

## 🗄️ Database

The project uses a MySQL/MariaDB database named:

```text
alm
```

The database schema and sample records are included in:

```text
alm.sql
```

### Main Database Tables

The SQL dump contains tables for:

- `adminlogin` — administrator login information
- `alumnilogin` — registered alumni information
- `events` — alumni events
- `achievements` — alumni achievements
- `postedjobs` — job opportunities posted by alumni
- `mentorrequests` — mentor/event requests
- `queries` — queries submitted by users
- `images` — uploaded image information

## ⚙️ Requirements

Before running the project, install a local PHP development environment such as:

- XAMPP
- WAMP
- Laragon

Recommended components:

- PHP 8.x
- MySQL or MariaDB
- Apache
- phpMyAdmin
- A modern web browser

## 🚀 Installation & Setup

### 1. Clone or Download the Project

Place the project inside your web server's document root.

For XAMPP:

```text
C:\xampp\htdocs\
```

For example:

```text
C:\xampp\htdocs\Alumni-Management-System\
```

### 2. Start Apache and MySQL

Open XAMPP Control Panel and start:

```text
Apache
MySQL
```

### 3. Create the Database

Open phpMyAdmin:

```text
http://localhost/phpmyadmin
```

Create a database named:

```text
alm
```

Then import:

```text
alm.sql
```

### 4. Configure Database Connection

Open:

```text
dbconnect.php
```

The current project is configured for a local MySQL/MariaDB server:

```php
$servername = 'localhost';
$username = 'root';
$password = '';
$dbname = 'alm';
```

If your MySQL configuration is different, update these values accordingly.

### 5. Run the Project

Open the project in your browser:

```text
http://localhost/Alumni-Management-System/
```

If the extracted project directory has a different name, replace `Alumni-Management-System` with that directory name.

## 🔐 Authentication

The application uses PHP sessions to control access to alumni and administrator pages.

Examples include:

- Alumni login → `alumnilogin.php`
- Admin login → `adminlogin.php`
- Logout → `logout.php`

The database dump contains sample login records for development/testing. **Change or remove sample credentials before deploying the application publicly.**

## 🔄 Basic Workflow

```text
                    ┌──────────────────────┐
                    │   Alumni Management   │
                    │        System         │
                    └──────────┬───────────┘
                               │
              ┌────────────────┴────────────────┐
              │                                 │
       ┌──────▼──────┐                   ┌──────▼──────┐
       │    Alumni   │                   │    Admin    │
       └──────┬──────┘                   └──────┬──────┘
              │                                 │
       ┌──────▼──────────────┐           ┌──────▼──────────────┐
       │ Register / Login    │           │ Admin Login         │
       │ View Events         │           │ View Queries        │
       │ View Gallery        │           │ View Achievements   │
       │ Post Jobs           │           │ View Job Posts      │
       │ Share Achievements  │           │ View Mentor Requests│
       │ Send Queries        │           │ Add/Delete Events   │
       │ Become a Mentor     │           └─────────────────────┘
       └─────────────────────┘
```

## 📋 Main Modules

### Alumni Registration

New alumni can register using their name, email, department, batch, and password. The registration process includes basic input validation and duplicate email checking.

### Job Portal

Alumni can share employment opportunities by submitting:

- Company name
- Job position
- Job description
- Salary range
- Required skills
- Contact email

Administrators can view the submitted job postings and export the displayed information.

### Achievement Sharing

Alumni can submit achievements along with a description and supporting file/certificate.

### Mentor Program

Alumni can submit a mentor request with:

- Event name
- Organizer
- Email
- Description
- Start date
- End date

### Event Management

Administrators can add and delete events. Events include information such as:

- Event name
- Organizer
- Description
- Start date
- End date
- Event image/file

Upcoming events can then be displayed through the alumni portal.

### Query Management

Users can submit queries through the portal. Administrators can view submitted queries from the admin dashboard.

## 🛡️ Security Notes

This project is suitable as an academic/demo web application, but additional security work is recommended before production deployment.

Recommended improvements include:

- Replace MD5 password hashing with PHP `password_hash()` and `password_verify()`
- Use prepared statements instead of directly inserting user input into SQL queries
- Add CSRF protection to forms
- Strengthen session security
- Validate and sanitize uploaded files more strictly
- Store uploaded files outside publicly accessible directories where appropriate
- Restrict executable file uploads
- Add authorization checks to every protected administrative action
- Remove sample/default credentials
- Use HTTPS in production
- Move database credentials into environment/configuration variables rather than committing them to source control

## 🧪 Development

For local development, modify the PHP files and refresh the browser after saving changes.

The database can be managed through:

```text
phpMyAdmin
```

and the application can be tested through:

```text
http://localhost/
```

## 🎯 Use Cases

This system can be used by:

- Universities
- Colleges
- Schools
- Academic departments
- Alumni associations
- Educational organizations

It provides a centralized platform for maintaining alumni engagement and sharing opportunities between alumni and their institution.

## 🔮 Possible Future Improvements

- Alumni profile editing
- Alumni search and directory
- Advanced role-based access control
- Password reset through email
- Secure password hashing
- Email notifications
- Real-time messaging
- Alumni networking
- Event registration
- Job application tracking
- Advanced admin analytics/dashboard
- Responsive/mobile-first UI improvements
- REST API integration
- Cloud-based file storage
- Automated database backups

## 📄 License

This project does not currently include a specific open-source license.

If you plan to publish or distribute it publicly, add an appropriate license such as MIT, Apache-2.0, or another license that matches your intended usage.

## 👨‍💻 Project

**Project Title:** Alumni Management System

**Type:** Web Application

**Backend:** PHP

**Database:** MySQL/MariaDB

**Frontend:** HTML, CSS, JavaScript
