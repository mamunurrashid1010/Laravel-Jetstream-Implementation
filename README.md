# Jetstream Implementation in Laravel 8
 In this project, here i implement Jetstream in laravel 8. And also here i show that step by step how to integrate jetstream.

#####Note: New Applications Only
Jetstream should only be installed into new Laravel applications. Attempting to install Jetstream into an existing Laravel application will result in unexpected behavior and issues.

## How to Integrate Jetstream in Laravel 8
##### 1. Create new laravel project via composer
```
composer create-project laravel/laravel Laravel-Jetstream-Implementation
```

Go to project directory ```cd Laravel-Jetstream-Implementation``` or open project with IDE.

##### 2. Install jetstream package
```
composer require laravel/jetstream
```

##### 3. After installed the Laravel jetstream package, choose and run one command
```
// LIVEWIRE
// Install JetStream with the Livewire stack without teams
php artisan jetstream:install livewire
// Install JetStream with the LiveWire stack and teams
php artisan jetstream:install livewire --teams

// INERTIA
// Install JetStream with the Inertia stack without teams
php artisan jetstream:install inertia
// Install Jetstream with the Inertia stack and teams
php artisan jetstream:install inertia --teams
```

##### 4. Next, build your assets with the following commands
```
npm install
npm run dev
```

##### 5. Open ```resources\views\layouts\app.blade.php``` and ```resources\views\layouts\guest.blade.php``` and add this code
```
// add this code
<link rel="stylesheet" href="{{ asset('css/app.css') }}">
<script src="{{ asset('js/app.js') }}" defer></script>
```
and also remember to add comment @vite line
```
//comment
{{--  @vite(['resources/css/app.css', 'resources/js/app.js'])--}}
```

##### 6. Create a new database
Here I'm using my MySQL PHPMyAdmin to create a database.<br>
Open ``` .env ``` file and add your database credentials.
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=testdb
DB_USERNAME=root
DB_PASSWORD=
```
Run migration artisan command
```
php artisan migrate
```

Then run  ```php artisan serve``` & you can see the project on ```http://127.0.0.1:8000```
###### Completed.

Official Documentation: https://jetstream.laravel.com/2.x/installation.html
