# OrganiseEvents
OrganiseEvents is a Laravel-based starting point for an event organisation application. The current version provides the Laravel application foundation, SQLite database configuration, frontend asset tooling, and the default user model and migrations.

## Overview
### Problem

Event information can become difficult to manage when it is spread across disconnected pages, files, or manual processes. A central application is needed to provide a clear foundation for managing event-related data.

### Solution
OrganiseEvents establishes a web application foundation that can be extended with event creation, scheduling, registration, and calendar management features. At the current stage, the project contains the base Laravel structure and is ready for those domain features to be implemented.

## Features

The current implementation includes:

- Laravel 12 application structure.
- SQLite database configuration.
- Default `User` model with factory support.
- Database migrations for users, sessions, password reset tokens, cache, and jobs.
- PHPUnit test configuration.

The following event-management features are planned but are not implemented yet:

- Event creation, editing, and deletion.
- Calendar views and scheduling.
- Event registration and attendance tracking.
- Authentication pages and user roles.
- Event search, filtering, and notifications.
- A dedicated JSON API.

## Architecture / How It Works

OrganiseEvents follows Laravel's MVC-oriented architecture:

1. Requests enter through the public front controller in `public/index.php`.
2. Laravel loads the application configuration from `bootstrap/app.php`.
3. Web routes are defined in `routes/web.php`.
4. Controllers and models belong in `app/Http/Controllers` and `app/Models`.
5. Database structure is managed through migrations in `database/migrations`.


At present, the root route returns the `welcome` Blade view. No event-specific request flow has been added yet.

## Tech Stack

- **Backend:** PHP 8.2+ and Laravel 12.
- **Templating:** Blade.
- **Database:** SQLite by default, with Laravel support for other database drivers.
- **HTTP client:** Axios.
- **Testing:** PHPUnit 11 and Laravel's testing tools.
- **Dependency management:** Composer and npm.

## Prerequisites

Install the following before starting the project:

- PHP 8.2 or newer.
- Composer.
- Node.js and npm.
- SQLite support enabled in PHP (`pdo_sqlite` and `sqlite3`).

You can verify the PHP SQLite extensions with:

```bash
php -m
```

## Installation

From the project directory:

```bash
composer install
npm install
```

Create the local environment file:

```bash
cp .env.example .env
```

On Windows PowerShell, use:

```powershell
Copy-Item .env.example .env
```

Generate the application key:

```bash
php artisan key:generate
```

Create the SQLite database file if it does not exist:

```bash
php -r "file_exists('database/database.sqlite') || touch('database/database.sqlite');"
```

Run the database migrations:

```bash
php artisan migrate
```

## Running the Application

Start the Laravel development server:

```bash
php artisan serve
```



The application is then available at `http://localhost:8000`.

To compile production frontend assets:

```bash
npm run build
```

## Testing

Run the test suite with:

```bash
php artisan test
```

The current tests cover the default Laravel example behavior. Feature-specific tests should be added as event functionality is implemented.

## API Documentation

There is currently no dedicated JSON API.

### Available Route

| Method | Endpoint | Response |
| --- | --- | --- |
| `GET` | `/` | The default Blade welcome page |

Event, authentication, registration, and calendar API endpoints will be documented here when they are added.

## Project Status

This repository is an initial Laravel foundation for OrganiseEvents. The environment and default application flow are configured, but the core event-management domain has not been implemented yet.
