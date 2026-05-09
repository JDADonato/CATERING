# Eloquente Catering System (ECS)

A full-stack catering booking and management system built with Laravel 12, Inertia.js, and React.

## Tech Stack

- **Backend:** Laravel 12, PHP 8.2
- **Frontend:** React 19, Inertia.js, Tailwind CSS
- **Database:** SQLite
- **Build Tool:** Vite 7

---

## How to Run (Step by Step)

### Prerequisites

Make sure you have the following installed on your computer:

| Tool | Download Link | Purpose |
|------|---------------|---------|
| **Node.js** (v18+) | [nodejs.org](https://nodejs.org/) | Runs the frontend build tools |
| **Composer** | [getcomposer.org](https://getcomposer.org/) | Manages PHP dependencies |
| **PHP 8.2+** | Included with [XAMPP](https://www.apachefriends.org/) | Runs the Laravel backend |

> **Important:** If using XAMPP, make sure `C:\xampp\php` is added to your system PATH so you can run `php` from any terminal.  
> If your project includes a local `php/` folder, you can use `.\php\php.exe` instead.

---

### Step 1: Install Dependencies

Open a terminal in the project folder (`ECS-main`) and run:

```bash
composer install
npm install
```

This downloads all PHP and JavaScript packages needed.

---

### Step 2: Set Up the Environment

```bash
cp .env.example .env
php artisan key:generate
```

This creates your environment config file and generates an encryption key.

---

### Step 3: Set Up the Database

```bash
php artisan migrate
```

This creates the SQLite database and all required tables.

---

### Step 4: Start the Application

You need **two terminals** running at the same time:

**Terminal 1 — Start the PHP backend:**
```bash
php artisan serve
```
> Or if using a local PHP folder: `.\php\php.exe artisan serve`

**Terminal 2 — Start the frontend dev server:**
```bash
npm run dev
```

---

### Step 5: Open the Website

Go to **http://127.0.0.1:8000** in your browser.

| Service | URL |
|---------|-----|
| Laravel Server | http://127.0.0.1:8000 |
| Vite Dev Server | http://localhost:5173 (auto-proxied) |

---

## Default Accounts

After running migrations, you can register a new account as a **Client** through the website.

For admin/staff access, seed the database or create accounts via the admin panel.

---

## Features

- **Landing Page** — Hero carousel, about section, gallery
- **Menu Gallery** — Browse dishes, filter by category/price, build custom packages
- **Multi-Step Booking Wizard** — Schedule → Event Type → Headcount → Menu → Location → Submit
- **Custom Package Builder** — Build your own menu from the Menu page and carry it into booking
- **Booking Summary** — Live cost calculation with overtime, transport, and high-rise surcharges
- **Client Dashboard** — Track bookings, payments, and event details
- **Ops Dashboard** — Manage bookings and update statuses (Marketing/Admin)
- **Finance Dashboard** — Verify payments, manage ledger, process refunds
- **Admin Dashboard** — Employee management, pricing overrides, analytics

---

## Project Structure

```
ECS-main/
├── app/                    # Laravel backend (Controllers, Models, Middleware)
├── database/               # Migrations and seeders
├── resources/
│   ├── js/                 # React frontend
│   │   ├── Pages/          # Page components (routed via Inertia)
│   │   ├── Components/     # Reusable UI components
│   │   ├── context/        # Auth & Toast context providers
│   │   ├── data/           # Static mock data (dishes, packages)
│   │   └── utils/          # Utility functions
│   ├── css/                # Stylesheets
│   └── images/             # Static assets
├── routes/
│   └── web.php             # All route definitions
├── public/                 # Public assets
└── .env                    # Environment configuration
```

## License

This project is proprietary software for Eloquente Catering.
