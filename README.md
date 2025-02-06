# ActivityLogs

This project integrates Spatie's Laravel Activitylog and Laravel Permission packages to provide activity logging and role-based access control for your Laravel application.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project leverages Spatie's Laravel Activitylog and Laravel Permission packages to:
- Log user activities
- Manage roles and permissions

## Installation

### Prerequisites

- Laravel >= 8.0
- Composer

### Steps

1. Clone the repository:

```bash
git clone https://github.com/sadiqueali786/activitylogs.git
cd activitylogs
Install the required packages:

bash
composer require spatie/laravel-activitylog spatie/laravel-permission
Publish the configuration files:

bash
php artisan vendor:publish --provider="Spatie\Activitylog\ActivitylogServiceProvider"
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
Run the migrations:

bash
php artisan migrate
Configuration
Setting Up Roles and Permissions
Define your roles and permissions in the config/permission.php file.

Configuring Activity Log
You can customize the activity log settings in the config/activitylog.php file.

Usage
Assigning Roles and Permissions
You can assign roles and permissions to users:

php
use Spatie\Permission\Models\Role;
use Spatie\Permission\Models\Permission;

$role = Role::create(['name' => 'writer']);
$permission = Permission::create(['name' => 'edit articles']);

$role->givePermissionTo($permission);
$user->assignRole('writer');
Logging Activities
Log activities in your controllers or services:

php
use Spatie\Activitylog\Models\Activity;

activity()
    ->causedBy($user)
    ->performedOn($model)
    ->log('created an article');
Retrieving Activity Logs
Retrieve logs for a model or user:

php
$activities = Activity::where('causer_id', $user->id)->get();
Contributing
We welcome contributions! Please follow these steps to contribute:

Fork the repository

Create a new branch (git checkout -b feature-name)

Commit your changes (git commit -am 'Add some feature')

Push to the branch (git push origin feature-name)

Create a new Pull Request

License
This project is licensed under the MIT License - see the LICENSE.md file for details.

Acknowledgments
Spatie for their excellent packages

All contributors to this project
