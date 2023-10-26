# Laravel Administration

![Laravel Logo](src/readme-assets/images/laravel_administration_portal.jpg)
[![Total Downloads](https://img.shields.io/packagist/dt/laravel/framework)](https://packagist.org/packages/laravel/framework)
[![Latest Stable Version](https://img.shields.io/packagist/v/laravel/framework)](https://packagist.org/packages/laravel/framework)
[![License](https://img.shields.io/packagist/l/laravel/framework)](https://opensource.org/licenses/MIT)

## About Laravel Administration

Laravel Administration is a powerful package designed to simplify the development of Laravel applications by automating common CRUD (Create, Read, Update, Delete) operations. With this package, you can create models effortlessly and enjoy automatic route generation, views, and controller logic.

## Features

- Automatic CRUD operations.
- RESTful API generation.
- Easy-to-use schema builder for advanced customization.
- User authentication and role management.
- MIT-licensed open-source software.

## Installation Guide

To get started with Laravel Administration, follow these steps:

0. **Create a Laravel Project**:

   ```sh
   composer create-project laravel/laravel LaravelAdministration

1. **Install LaravelAdministration Package**:

    Install the LaravelAdministration package using Composer:

   ```sh
   composer require bitsoftsol/laravel-administration

2. **Add LaravelAdminServiceProvider**:

    Open the `config/app.php` file and add the LaravelAdministration service provider to the `providers` array:

   ```php
   'providers' => [
       // ...
       Bitsoftsol\LaravelAdministration\LaravelAdminServiceProvider::class,
   ],

3. **Publish Vendor Files:**:

    Run the following Artisan command to publish vendor files:

   ```sh
   php artisan vendor:publish

   Select the LaravelAdminServiceProvider when prompted.

4. **Build Assets:**:

    Run the following commands to build assets:

   ```sh
   npm install
   npm run dev

5. **Set Database Connection:**:

    Configure your database connection by setting the database name in your `.env` file.

6. **Run Migrations:**:

    Execute the database migrations and seed data:

   ```sh
   php artisan migrate --seed

7. **Enable Authentication Routes:**:

    Add the following line inside your `routes/web.php` file:

   ```php
   Auth::routes();

8. **Serve Your Project:**:

    Serve your Laravel project:

   ```sh
   php artisan serve

9. **Access Laravel Administration:**:

    Open your browser and access the URL `(host)/admin` (e.g., `http://127.0.0.1:8000/admin`).

10. **Login Credentials:**:

    Use the following credentials to log in:
    + Username: admin@bitsoftsol.com
    + Password: bitsoftsol123

11. **Congratulations!:**:

    You have successfully installed Laravel Administration.


