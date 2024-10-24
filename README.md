<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Docker Overview

Docker is a platform that enables developers to automate the deployment of applications inside lightweight, portable containers. Containers package all necessary components of an application, including the code, runtime, libraries, and configurations, making them independent of the host operating system.

### Key Benefits of Docker:

1. **Portability**: Docker containers can run on any system with Docker installed, ensuring consistency across different environments.
2. **Isolation**: Each service (web server, database, etc.) runs in its own container, avoiding conflicts between dependencies.
3. **Efficiency**: Docker uses fewer resources than virtual machines, making it faster and more efficient.
4. **Easy Deployment**: Applications can be packaged with all their dependencies and configurations, making them easy to deploy across various environments.

### How Docker Is Used in This Project:

- **PHP-FPM (Laravel App)**: The Laravel application runs inside a PHP-FPM container, handling all the PHP processes.
- **MySQL**: A containerized MySQL instance is used as the project's database, and its configuration is stored in the `.env` file.
- **phpMyAdmin**: This provides a convenient web-based interface for managing the MySQL database, accessible through `http://localhost:8080`.

The Dockerized setup ensures that the entire application and its dependencies are isolated, portable, and easy to replicate across different machines. This project uses **Docker Compose** to manage the multiple containers, simplifying the setup process and allowing you to run everything with a single command.

### Project Structure:

- **Dockerfile**: Defines the environment for the Laravel application.
- **docker-compose.yml**: Coordinates the setup of multiple containers (Laravel app, MySQL, phpMyAdmin).
- **.env**: Stores environment variables such as database credentials, making it easy to switch between environments without changing the code.

### Accessing the Application:

Once the Docker containers are running, you can access:

- **Laravel Application**: `http://localhost:8000`
- **phpMyAdmin**: `http://localhost:8081` (login with the database credentials specified in `.env`)

## About This Project

This project is a Laravel application running in a Dockerized environment. The setup ensures a smooth and efficient development process by utilizing containerized services for the application and its dependencies. Here's an overview of the components:

- **Laravel Application**: The main web application running in a PHP-FPM container.
- **MySQL Database**: A containerized MySQL database for storing application data.
- **phpMyAdmin**: A containerized web-based interface for managing the MySQL database.

<img src="https://github.com/AliSubtain/Laravel-Docker/raw/dev/public/images/aboutProject.png" width="400" alt="About Project" style="max-width: 100%;">

By containerizing the services, this project makes it easy to manage dependencies, isolate environments, and streamline both development and deployment processes.

## Directory Structure

```
├── app/                   # Application source code (Models, Controllers, etc.)
├── artisan                # Artisan command-line utility
├── bootstrap/             # Files for bootstrapping the framework
├── composer.json          # Composer dependencies configuration file
├── composer.lock          # Composer lock file (freezes the dependency versions)
├── config/                # Application configuration files
├── data/                  # Application-specific data (usage may vary)
├── database/              # Database migrations, seeders, and factories
├── docker/                # Docker-related configuration files
├── docker-compose.yml     # Docker Compose file to orchestrate multi-container setups
├── Dockerfile             # Docker configuration for the app environment
├── index.html             # Default HTML file for public access
├── package.json           # Node.js dependencies and scripts configuration
├── phpunit.xml            # PHPUnit configuration for testing
├── postcss.config.js      # PostCSS configuration for processing CSS
├── public/                # Publicly accessible files (assets, index.php, etc.)
├── README.md              # Project documentation file
├── resources/             # Views, raw assets (SASS, JS, images), and language files
├── routes/                # Web and API route definitions
├── storage/               # Logs, compiled templates, and other storage files
├── supervisord.log        # Log file for Supervisor (process manager)
├── tailwind.config.js     # Tailwind CSS configuration
├── tests/                 # Unit and feature test cases
├── vendor/                # Composer dependencies (auto-generated)
└── vite.config.js         # Vite configuration file for bundling assets
```

### Project Features

- **Consistent Environment**: The same environment for development, testing, and production using Docker containers.
- **Database Management**: Manage your MySQL database via phpMyAdmin without installing additional tools.
- **Easy to Scale**: Docker Compose allows you to scale up or down services effortlessly.
