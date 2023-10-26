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

    Add the following line inside the providers array within `config/app.php`:

   ```php
   Bitsoftsol\LaravelAdministration\LaravelAdminServiceProvider::class

3. **Publish Configuration Files:**:

    Run the command and select `LaravelAdminServiceProvider`:

   ```sh
   php artisan vendor:publish

4. **Build Assets:**:

    Run the following commands to build assets:

   ```sh
   npm install
   npm run dev
