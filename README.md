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

3. **Publish Vendor Files**:

    Run the following Artisan command to publish vendor files:
    Select the `LaravelAdminServiceProvider` when prompted.

   ```sh
   php artisan vendor:publish

4. **Install Frontend Assets**:

    Run the following commands to build assets:

   ```sh
   npm install
   npm run dev

5. **Set Database Connection**:

    Configure your database connection by setting the database name in your `.env` file.

6. **Run Migrations**:

    Execute the database migrations and seed data:

   ```sh
   php artisan migrate --seed

7. **Enable Authentication Routes**:

    Add the following line inside your `routes/web.php` file:

   ```php
   Auth::routes();

8. **Serve Your Project**:

    Serve your Laravel project:

   ```sh
   php artisan serve

9. **Access Laravel Administration**:

    Open your browser and access the URL `(host)/admin` (e.g., `http://127.0.0.1:8000/admin`).

10. **Login Credentials**:

    Use the following credentials to log in:
       + Username: admin@bitsoftsol.com
       + Password: bitsoftsol123

11. **Create a Superuser**:

    To create a superuser for your Laravel application, follow these steps:

     * Open your terminal and navigate to the root directory of your Laravel project.
   
     * Run the following command:
   
      ```sh
      php artisan createsuperuser
     
The `createsuperuser` command will prompt you to provide the following information:

* __Username__: Choose a unique username for the superuser.
* __Email__: Enter the email address associated with the superuser.
* __Password__: Set a secure password for the superuser.
* __Confirm Password__: Re-enter the password for confirmation.

+ After successfully providing the required information, the superuser account will be created.
+ You can now use the provided username and password to log in as the superuser and access the admin privileges.
+ Creating a superuser allows you to manage and control various aspects of your Laravel application with elevated permissions.

12. **Congratulations!**:

    If you can log in and access the Laravel Administration dashboard, congratulations! You have successfully installed Laravel Administration.

## Usage Guide - Basic

In this section, we will guide you through performing automatic CRUD operations for the `Seller` model using Laravel Administration.

0. **Generate the Seller Model:**

   Run the following Artisan command to create the `Seller` model along with its migration file:

   ```bash
   php artisan make:model Seller -m

1. **Define Seller Table Fields:**

   Inside the generated migration file, define the `Seller` table fields, including `name`, `email`, `city`, `country`, and `profile_image`.

2. **Add LaravelAdmin and LaravelAdminAPI Traits:**

   Inside the generated migration file, define the `Seller` table fields, including `name`, `email`, `city`, `country`, and `profile_image`.
   Enhance the functionality of your `Seller` model by importing the `LaravelAdmin` and `LaravelAdminAPI` traits.
   + Import the `LaravelAdmin` Trait at the top of the `Seller` model class:

      ```php
      use Bitsoftsol\LaravelAdministration\Traits\LaravelAdmin;

   + Import the `LaravelAdminAPI` Trait on top of the `Seller` model class:

      ```php
      use Bitsoftsol\LaravelAdministration\Traits\LaravelAdminAPI;

   + Add these two lines inside the Seller model class to include the traits:

      ```php
      use LaravelAdmin;
      use LaravelAdminAPI;

   














