# Installation Guide

This guide will walk you through the process of setting up a Laravel project. Please follow these steps to ensure a smooth installation.

## Prerequisites

Before you start, make sure you have the following prerequisites installed on your system:

- [XAMPP](https://www.apachefriends.org/index.html) with PHP version 7.4.33
- [Composer](https://getcomposer.org/) (PHP dependency manager)

## Installation Steps

1. **XAMPP Installation:**

   Download and install XAMPP with PHP version 7.4.33 by following the official [XAMPP installation instructions](https://www.apachefriends.org/index.html).

2. **Composer Installation:**

   If you don't have Composer installed, you can download and install it from [getcomposer.org](https://getcomposer.org/download/).

3. **Clone the Laravel Project:**

   Use the following command to clone your Laravel project from a repository or create a new one:

   ```bash
   git clone git@github.com:dputz/jkpportal-production.git
   cd jkpportal-production

4. **Install Project Dependencies:**

   Run the following command to install Laravel project dependencies using Composer:
   ```bash
   composer update --ignore-platform-reqs

4. **Configure the Environment:**

   Copy the `.env.example` file to a new `.env` file and configure your environment settings, such as the database connection and application key. You can generate an   application key using the following command:
   ```bash
   php artisan key:generate
   
5. **Migrate the Database:**

   Run the following command to migrate your database and create the necessary tables:
   ```bash
   php artisan migrate

5. **Start the Development Server:**

   You can start the Laravel development server using the following command:
   ```bash
   php artisan serve
   This will start a local development server, and you can access your Laravel application in your web browser at `http://localhost:8000`.
  

## Setup Auto Deployment
you need to follow these steps to setup auto deployment 

- create a .github folder and .workflows folder inside it on root directoy like .github/workflows
- create a config.yml file inside the workflows folder and paste this code 
```python
name: Deploy to Nginx

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Set up SSH connection
      uses: appleboy/ssh-action@master
      with:
        host: ${{ secrets.SSH_HOST }}
        username: ${{ secrets.SSH_USERNAME }}
        key: ${{ secrets.SSH_PRIVATE_KEY }}
        script: |
          cd /var/www/project-name
          bash deploy.sh
```
- create a file named deploy.sh on the root directory and paste this code 
```pythone

#!/bin/bash

cd /var/www/project-name/
git pull origin main

composer install --ignore-platform-reqs

sudo service nginx restart

php artisan cache:clear

echo "Auto deploy completed successfully!"
```

- open repository on github, go to settings and then secrets and add these secrest
    - SSH_HOST 
    - SSH_USERNAME
    - SSH_PRIVATE_KEY

- add server public key in authorized_key file 

- push the code the check Actions from github that's it





<p align="center"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable, creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, yet powerful, providing tools needed for large, robust applications. A superb combination of simplicity, elegance, and innovation give you tools you need to build any application with which you are tasked.

## Learning Laravel

Laravel has the most extensive and thorough documentation and video tutorial library of any modern web application framework. The [Laravel documentation](https://laravel.com/docs) is thorough, complete, and makes it a breeze to get started learning the framework.

If you're not in the mood to read, [Laracasts](https://laracasts.com) contains over 900 video tutorials on a range of topics including Laravel, modern PHP, unit testing, JavaScript, and more. Boost the skill level of yourself and your entire team by digging into our comprehensive video library.

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](http://laravel.com/docs/contributions).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell at taylor@laravel.com. All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
