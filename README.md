# Recruitment Management System (RMS)

## Overview
The **Recruitment Management System (RMS)** is a PHP-based web application that enables companies to manage the recruitment process effectively. This system allows HR managers, recruiters, and interviewers to post jobs, track candidates, schedule interviews, and handle hiring decisions through an easy-to-use web interface.

## Features
1. **Job Postings**: HR Managers can create, edit, and delete job postings with descriptions, required skills, qualifications, and application deadlines.
2. **Candidate Applications**: Candidates can apply for jobs by submitting their details and resumes.
3. **Application Status Tracking**: Track the status of applications through stages like "Applied", "Shortlisted", "Interview Scheduled", and "Hired".
4. **Interview Scheduling**: Schedule and manage interviews for shortlisted candidates.
5. **Role-based Access Control**: Different user roles with access restrictions: Admin, HR Manager, Recruiter.
6. **Reports**: Generate reports on hiring progress, interview status, and other recruitment metrics.

## Installation

### Prerequisites
Ensure that the following software is installed on your system:
- **PHP** (v7.4+ recommended)
- **MySQL** 
- **Apache**  server (for web hosting)
- **PHPMyAdmin** (optional, for database management)

### Steps

1. **Clone the Repository**  
   If you're using Git, you can clone the repository:
   ```bash
   git clone https://github.com/your-username/recruitment-management-system.git
   cd recruitment-management-system
   ```

2. **Set Up the Database**  
   - Create a new database in MySQL or MariaDB:
   ```sql
   CREATE DATABASE rms;
   ```
   - Import the database schema from the `database.sql` file in the repository:
   ```bash
   mysql -u your-username -p rms < database.sql
   ```
   - Or use **phpMyAdmin** to import the `database.sql` file.

3. **Configure the Database Connection**  
   Open the `config.php` file in the root directory and update the database connection details:
   ```php
   <?php
   define('DB_SERVER', 'localhost');
   define('DB_USERNAME', 'root'); // your MySQL username
   define('DB_PASSWORD', '');     // your MySQL password
   define('DB_DATABASE', 'rms');  // the name of your database
   ?>
   ```

4. **Configure the SMTP (Optional)**  
   If you plan to send email notifications (e.g., interview scheduling), configure the SMTP settings in `config.php`:
   ```php
   define('SMTP_HOST', 'smtp.example.com');
   define('SMTP_PORT', '587');
   define('SMTP_USERNAME', 'your-email@example.com');
   define('SMTP_PASSWORD', 'your-email-password');
   ```

5. **Set Permissions**  
   Ensure the `uploads` directory (for candidate resumes) has the correct file permissions:
   ```bash
   chmod -R 755 uploads/
   ```

6. **Start the Web Server**  
   If using Apache, make sure the Apache server is running:
   ```bash
   sudo systemctl start apache2
   ```

7. **Access the Application**  
   Open your browser and navigate to `http://localhost/recruitment-management-system` to access the system.

### Environment Variables
You can also set these values in your `.env` file if you are using any PHP environment management tool.
- **DB_SERVER**: Database server (e.g., `localhost`)
- **DB_USERNAME**: Database username
- **DB_PASSWORD**: Database password
- **DB_DATABASE**: The name of the database
- **SMTP_HOST**: SMTP server for email notifications
- **SMTP_PORT**: SMTP server port
- **SMTP_USERNAME**: SMTP username
- **SMTP_PASSWORD**: SMTP password

## Usage

### User Roles and Permissions
- **Admin**: Has full access to all features, including user management, job postings, and reporting.
- **HR Manager**: Can manage job postings, view candidate applications, schedule interviews, and make hiring decisions.
- **Recruiter**: Can view candidate applications and assist in the interview process.
- **Candidate**: Can apply for jobs, upload resumes, and track the status of their applications.

### Job Postings
- HR Managers can create and manage job postings with detailed descriptions, requirements, and deadlines.
- Candidates can search job postings and apply directly through the system.

### Candidate Applications
- Candidates can apply by submitting personal details and resumes.
- HR Managers and Recruiters can review candidate profiles, mark them as shortlisted or rejected, and schedule interviews.

### Interview Scheduling
- Recruiters can schedule interviews and send email notifications to candidates.
- An interview can be scheduled and updated with feedback from interviewers.

### Reports and Analytics
- HR Managers and Admins can generate reports on candidate progress, interview outcomes, and hiring metrics.

## Technologies Used
- **Frontend**: HTML, CSS, JavaScript (with Bootstrap for responsive design)
- **Backend**: PHP (for handling the business logic)
- **Database**: MySQL (to store user information, job postings, candidate applications, etc.)


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

For more details, issues, or feature requests, please feel free to open an issue on the GitHub repository.

---

This is a basic outline for setting up and using a **Recruitment Management System** built with **PHP** and **MySQL**. You can expand this further based on your application's complexity, like integrating advanced user authentication, notification systems, or enhancing UI/UX with JavaScript frameworks like React or Vue.js.
