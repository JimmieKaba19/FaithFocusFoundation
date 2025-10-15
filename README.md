# FaithFocusFoundation Website

## Overview

Dynamic website for the NGO **FaithFocusFoundation** built with vanilla PHP. Features include home page, about us, programs, blog (admin CRUD), donations, and secure contact forms. Simple, secure, and scalable.

## Tech Stack

| Component           | Technology                     |
| ------------------- | ------------------------------ |
| **Backend**         | PHP 8+ (vanilla)               |
| **Frontend**        | HTML5, Bootstrap 5, JavaScript |
| **Database**        | MySQL (PDO)                    |
| **Email**           | PHPMailer                      |
| **Config**          | phpdotenv                      |
| **Server**          | LAMP (Apache)                  |
| **Dependencies**    |                                |
| **Version control** |                                |

## Folder Structure

```
faithfocusfoundation/
├── public/                  # Web root
│   ├── index.php
│   ├── .htaccess
│   ├── assets/
│   │   ├── css/
│   │   ├── js/
│   │   └── img/
│   └── uploads/
├── src/
│   ├── controllers/
│   ├── models/
│   ├── views/
│   │   ├── layouts/
│   │   └── admin/
│   └── helpers/
├── config/
├── logs/
├── tests/
├── vendor/
├── .env
├── .env.example
├── .gitignore
├── composer.json
├── composer.lock
└── README.md
```

## Quick Setup

### 1. Clone & Install

```bash
git clone faithfocusfoundation
cd faithfocusfoundation
composer install
```

### 2. Configure Environment

```bash
cp .env.example .env
# Edit .env with your DB credentials
- Fill in database credentials (e.g., DB_HOST, DB_NAME, DB_USER, DB_PASS).
- Add other secrets like email SMTP details.
```

### 3. Database Setup

```sql
-- Create database: faithfocus_db
-- Run schema.sql (create later)
```

### 4. Local Development

- **XAMPP/WAMP**: Set document root to `/public`
- Visit: `http://localhost`

### 5. Production Deploy

- Upload to server
- Document root: `/public`
- Enable HTTPS
- `chmod 755 dirs, 644 files`

## Security Checklist

- PDO prepared statements
- Input validation/sanitization
- CSRF tokens for forms
- Password hashing
- HTTPS enforced

## Development Timeline

| Phase           | Duration | Deliverables     |
| --------------- | -------- | ---------------- |
| 1. Setup        | 2-3 days | Project skeleton |
| 2. Core         | 4-5 days | Routing + DB     |
| 3. Static Pages | 3-4 days | Home/About       |
| 4. Dynamic      | 5-7 days | Blog + Forms     |
| 5. Admin        | 4-5 days | Secure dashboard |
| 6. Deploy       | 3-5 days | Live site        |

*Total: 4-6 weeks*

## Contributing

1. Branch: `feature/blog-crud`
2. Commit: `git commit -m "Add blog listing"`
3. PR to `develop` branch

*Built with ❤️ for FaithFocusFoundation | First updated: Oct 15, 2025*
