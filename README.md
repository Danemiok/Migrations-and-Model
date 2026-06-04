# Migrations and Model Project

A Laravel 12 application for managing school-related data: generations, classes, teachers, students, subjects, terms, and associations between students, classes, and teachers.

## Project Overview

This project is built on Laravel and includes:
- `app/Models` for core models like `Generation`, `Teacher`, `Student`, `ClassModel`, `Subjects`, `Term`, `StudentClass`, `TeacherClassSubject`, and `User`
- `database/migrations` for schema definitions and table structure
- `database/factories` for generating test and seed data
- `database/seeders` to populate initial records if needed
- default Laravel routing in `routes/web.php`

The app currently uses the default Laravel welcome view and is intended as a backend/data model project for school admin and class management.

## Setup Guide

1. Clone the repository:

   ```bash
   git clone https://github.com/your-repo/Migrations-and-Model.git
   cd Migrations-and-Model
   ```

2. Install PHP dependencies:

   ```bash
   composer install
   ```

3. Copy the environment file and generate the app key:

   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

4. Configure your database in `.env`:
   - For MySQL, set `DB_CONNECTION=mysql`, `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, and `DB_PASSWORD`
   - For SQLite, set `DB_CONNECTION=sqlite` and create `database/database.sqlite`

5. Run migrations:

   ```bash
   php artisan migrate
   ```

6. Install frontend dependencies and build assets:

   ```bash
   npm install
   npm run build
   ```

7. Start the development server:

   ```bash
   php artisan serve
   ```

### Optional commands

- Run database migrations fresh:
  ```bash
  php artisan migrate:fresh
  ```
- Run tests:
  ```bash
  php artisan test
  ```
- Start frontend dev mode:
  ```bash
  npm run dev
  ```

## What This Project Contains

- `app/Models`: Eloquent models representing domain entities
- `database/migrations`: Migration files to create tables
- `database/factories`: Factories for model generation and testing
- `database/seeders`: Seed classes for initial data
- `routes/web.php`: Application routes
- `resources/views`: Blade views (currently default welcome view)

### Core domain relationships

- `Generation` groups school years or batches
- `ClassModel` represents classes
- `Subjects` holds subject records
- `Term` stores academic term data
- `Student` stores student records
- `Teacher` stores teacher records
- `StudentClass` links students to classes
- `TeacherClassSubject` links teachers to class-subject assignments

## Useful Composer Scripts

- `composer setup` — installs dependencies, creates `.env`, generates key, migrates, installs npm packages, and builds assets
- `composer test` — runs the Laravel test suite

## Notes

- The current app is configured with the default Laravel welcome route (`/`).
- Update `routes/web.php` and add controllers as needed to build application pages or APIs.
- If you want to seed demo data, add seeders and run `php artisan db:seed`.

## License

This project is licensed under the MIT License.
