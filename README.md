<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Laravel.svg/800px-Laravel.svg.png" width="200" alt="Laravel Logo"></a><a href="https://vuejs.org/" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png" width="200" alt="Vue Logo"></a></p>

# Laravel 10 Vue.js Vite CRUD

## Overview

This documentation provides an overview of a CRUD (Create, Read, Update, Delete) application built using Laravel 10 on the backend and Vue.js with Vite on the frontend. The application allows users to perform CRUD operations on student records.

## Features

- Create new student records.
- Read existing student records.
- Update existing student records.
- Delete existing student records.

## Prerequisites

Before setting up the application, ensure you have the following installed:

- PHP (>=7.4)
- Composer
- Node.js (>=14)
- npm or yarn
- Laravel CLI
- Git

## Setup

1. Clone the repository:

   ```bash
   git clone <repository_url>

2. Navigate to the project directory:

    ```bash
    cd <project_directory>

3. Install PHP dependencies:

   ```bash
    composer install

4. Install JavaScript dependencies:

   ```bash
    npm install

5. Configure environment:

   Copy .env.example to .env. <br>
   Update database credentials in .env according to your environment.
6. Generate application key:

   ```bash
    php artisan key:generate

7. Run database migrations:

    ```bash
    php artisan migrate

8. Start development server:

    ```bash
    php artisan serve

9. Access the application:

   Visit http://127.0.0.1:8000 in your web browser.

## Usage

### Adding a New Student Record:
1. Navigate to the "Add Record" section on the webpage.
2. Enter the student's name, address, and phone number.
3. Click the "Save" button to add the record.

### Viewing Existing Student Records:
- Existing student records are displayed in the "Student List" section of the webpage.

### Updating a Student Record:
1. Click the "Edit" button next to the student record you want to update.
2. Update the student's information in the form.
3. Click the "Save" button to update the record.

### Deleting a Student Record:
1. Click the "Delete" button next to the student record you want to delete.
2. Confirm the deletion when prompted.

## Support

For any issues or questions, please contact [Linkedin/isherezahin/](https://www.linkedin.com/in/isherezahin/).

## License

This project is licensed under the [MIT license].
