# Laravel Book Review App

A Laravel web application for browsing books and submitting reviews with star ratings. Books can be filtered by popularity and rating across different time windows, and all data is cached for fast page loads.

## Features

- Browse and search books by title
- Filter books by popularity or highest rating (last month / last 6 months)
- View individual book pages with all reviews
- Submit reviews with a 1–5 star rating
- Star rating component rendered in the UI
- Rate limiting on review submissions (3 per hour per user/IP)
- Cache invalidation when books or reviews are updated

## Tech Stack

- **Backend:** Laravel
- **Frontend:** Blade templates, Tailwind CSS
- **Database:** Compatible with any Laravel-supported database

## Docker Setup (Optional)

A `docker-compose.yaml` is included to spin up a MariaDB database and Adminer.

### Starting the containers

```bash
docker compose up -d
```

Once running, Adminer is accessible at [http://localhost:8080](http://localhost:8080). Log in with:

- **Server:** `mysql`
- **Username:** `root`
- **Password:** `root`

## Getting Started

### Prerequisites

- PHP
- Composer
- Node.js & npm
- A configured database (local or via Docker above)

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/n1n5/book-review.git
cd book-review
```

2. **Install dependencies**

```bash
composer install
npm install
```

3. **Set up your environment**

```bash
cp .env.example .env
php artisan key:generate
```

Then update your `.env` file with the following:

```env
DB_CONNECTION=mariadb
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=book_review
DB_USERNAME=root
DB_PASSWORD=root
```

4. **Run migrations and seed the database**

```bash
php artisan migrate
php artisan db:seed
```

5. **Start the development server**

```bash
composer run dev
```

Visit [http://localhost:8000](http://localhost:8000) in your browser.
