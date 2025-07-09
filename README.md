# Laravel 9 Backend APIs

A modular, multi-tenant backend API boilerplate built with Laravel 9, designed to accelerate development of SaaS and multi-tenant applications. This repository includes boilerplate code for managing domains, products, categories, offers, inventory, and more, with robust support for tenant data isolation and AWS S3 integration.

## Features

- **Multi-Tenancy:** 
  - Isolates data and resources per tenant using [stancl/tenancy](https://tenancyforlaravel.com/).
  - Dynamically creates and manages AWS S3 buckets for each tenant.
- **Domain Management:** 
  - Seamless CRUD for domains, with support for primary and fallback domains.
- **Product & Inventory Management:** 
  - Modular services for products, categories, inventory, and deductibles.
- **Offer Management:** 
  - Flexible offers, promo codes, and voucher management, including product associations.
- **Role & Permission System:** 
  - Role-based access control using [spatie/laravel-permission](https://spatie.be/docs/laravel-permission/).
- **RESTful API Endpoints:** 
  - Organized under `/api` with versioning support.
  - Authentication via Laravel Sanctum.
- **Event-Driven:** 
  - Decoupled logic using Laravel Events for handling entity lifecycle.
- **Seeders and Boilerplate Data:** 
  - Quick start with seeders for roles, permissions, and sample posts.

## Getting Started

### Prerequisites

- PHP 8.0+
- Composer
- Laravel 9.x
- MySQL or PostgreSQL or SQLite
- AWS account (for S3 integration)
- Redis (optional, for queues/cache)

### Installation

1. **Clone the repository**
    ```bash
    git clone https://github.com/PrashantRatanparikhe/Laravel-9-Backend-APIs.git
    cd Laravel-9-Backend-APIs
    ```

2. **Install dependencies**
    ```bash
    composer install
    ```

3. **Copy `.env` and configure**
    ```bash
    cp .env.example .env
    # Edit .env and set DB, AWS, and tenancy configs
    ```

4. **Generate application key**
    ```bash
    php artisan key:generate
    ```

5. **Run migrations and seeders**
    ```bash
    php artisan migrate --seed
    ```

6. **Serve the application**
    ```bash
    php artisan serve
    ```

## API Overview

- All endpoints are prefixed with `/api`.
- Authentication uses Laravel Sanctum.
- Example endpoints:
  - `POST /api/login`
  - `GET /api/domain`
  - `POST /api/product`
  - `GET /api/inventory`
  - `POST /api/offer`

## Multi-Tenancy & S3 Buckets

- Each tenant gets a dedicated AWS S3 bucket for file storage.
- Tenancy is initialized by request data.
- Tenant-specific config is handled via bootstrappers (`TenancyBootstrappers`).

## Role and Permission Management

- Roles: `superadmin`, `admin`, `staff`
- Permissions defined in `database/seeders/RoleSeeder.php`

## Project Structure

- `app/Services/` - Business logic for main entities.
- `app/Models/` - Eloquent models.
- `app/Requests/` - Form request validation.
- `database/seeders/` - Seeder classes for roles, tenants, posts, etc.
- `routes/api.php` - API routes.

## Contributing

Contributions, issues, and feature requests are welcome. Please open an issue or submit a pull request.

---

_As always, don't forget to ship fast 😎. We hope this boilerplate saves you a lot of development time and lets you get to production much faster._
