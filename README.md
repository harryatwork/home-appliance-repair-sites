<div align="center">

# Home Appliance Repair Sites

**A complete, mobile-first website template for home appliance repair businesses — service booking, technician profiles, pricing, and WhatsApp integration out of the box.**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?style=flat-square&logo=php&logoColor=white)](https://php.net)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://mysql.com)
[![License](https://img.shields.io/badge/license-MIT-a855f7?style=flat-square)](LICENSE)

[Quick Start](#-quick-start) · [Features](#-features) · [Pages](#-page-breakdown) · [Configuration](#-configuration) · [Deploy](#-deployment)

</div>

---

## The Problem

Most local appliance repair businesses have no website, or have one that was built in 2012 and looks like it. Customers Google "AC repair near me", land on your page, and leave in 4 seconds because the site loads slow, looks terrible on mobile, or makes it impossible to book a service.

**This template fixes all of that.** A professional, fast, conversion-optimised website that any repair shop owner can deploy in an afternoon — no coding required, just fill in your details.

---

## Features

- 📱 **Mobile-first responsive** — every page designed for the device your customers are actually using
- 📋 **Service request form** — customer fills in appliance type, issue description, preferred time slot, and location; goes straight to your inbox
- 🔧 **Technician booking** — customer-visible technician cards with specialisations, ratings, and availability badges
- 💰 **Pricing tables** — transparent service pricing by appliance category, with "Get Quote" fallback for complex jobs
- 🖼️ **Before/after gallery** — carousel of repair jobs with before/after slider, builds trust instantly
- ⭐ **Customer testimonials** — star rating cards, filterable by appliance type
- 💬 **WhatsApp click-to-chat** — floating button opens WhatsApp direct with pre-filled message
- 📍 **Service area map** — embedded Google Maps with pinned service zones
- ✉️ **PHP contact backend** — form submissions delivered via PHP `mail()` with anti-spam honeypot
- 🚀 **No JavaScript frameworks** — vanilla JS only, loads in under 1s on mobile data

---

## Page Breakdown

| Page | File | Purpose |
|---|---|---|
| Home | `index.php` | Hero, service categories, trust badges, CTA |
| Services | `services.php` | Full service list with icons and descriptions |
| Book Now | `book.php` | Multi-step booking form |
| Pricing | `pricing.php` | Price tables by appliance category |
| Gallery | `gallery.php` | Before/after repair photo gallery |
| Technicians | `technicians.php` | Team cards with specialisations |
| Testimonials | `testimonials.php` | Customer reviews with star ratings |
| Contact | `contact.php` | Contact form + map + WhatsApp |
| Admin | `admin/` | Booking inbox, message management |

---

## Project Structure

```
home-appliance-repair-sites/
├── index.php                   # Homepage
├── services.php                # Services catalogue
├── book.php                    # Booking form (multi-step)
├── pricing.php                 # Pricing tables
├── gallery.php                 # Before/after gallery
├── technicians.php             # Team page
├── testimonials.php            # Customer reviews
├── contact.php                 # Contact + map
│
├── admin/
│   ├── index.php               # Booking dashboard
│   ├── messages.php            # Contact form inbox
│   └── login.php               # Admin login
│
├── includes/
│   ├── db.php                  # MySQL connection
│   ├── mailer.php              # PHP mail wrapper
│   ├── config.php              # Business config (name, phone, area)
│   └── header.php / footer.php # Shared layout
│
├── assets/
│   ├── css/
│   │   ├── main.css            # Core styles
│   │   └── responsive.css      # Breakpoints
│   ├── js/
│   │   ├── booking.js          # Multi-step form logic
│   │   ├── gallery.js          # Before/after slider
│   │   └── whatsapp.js         # WhatsApp float button
│   └── images/
│       ├── services/           # Appliance icons
│       └── gallery/            # Before/after photos
│
└── database/
    └── schema.sql              # Tables: bookings, messages, technicians
```

---

## Quick Start

### 1 — Clone and configure

```bash
git clone https://github.com/harryatwork/home-appliance-repair-sites
cd home-appliance-repair-sites
```

Edit `includes/config.php` with your business details:

```php
define('BUSINESS_NAME',    'Cool Fix Appliance Repair');
define('BUSINESS_PHONE',   '+91 98765 43210');
define('BUSINESS_EMAIL',   'contact@coolfix.in');
define('WHATSAPP_NUMBER',  '919876543210');   // no + or spaces
define('SERVICE_AREAS',    ['Mumbai', 'Thane', 'Navi Mumbai']);
define('GOOGLE_MAPS_KEY',  'AIza...');
```

### 2 — Set up the database

```bash
mysql -u root -p < database/schema.sql
```

Then fill in DB credentials in `includes/db.php`.

### 3 — Deploy to any PHP host

Upload to your hosting via FTP or cPanel File Manager. Point your domain at the folder. Done.

### 4 — Test the booking form

Go to `/book.php`, submit a test booking. Check your inbox and the admin dashboard at `/admin/`.

---

## Configuration

| Variable | File | Description |
|---|---|---|
| `BUSINESS_NAME` | `config.php` | Appears in header, footer, email subjects |
| `WHATSAPP_NUMBER` | `config.php` | Phone number (no + or spaces) for click-to-chat |
| `SERVICE_AREAS` | `config.php` | Array of postcodes/cities shown on booking form |
| `ADMIN_EMAIL` | `config.php` | Where booking notifications are sent |
| `ADMIN_PASSWORD` | `config.php` | Plain text (hash it before going live) |
| `GOOGLE_MAPS_KEY` | `config.php` | API key for embedded service area map |
| Primary colour | `assets/css/main.css` | Change `--brand: #E55A1C;` to your brand colour |

---

## Deployment

Works on any PHP 7.4+ shared hosting — Hostinger, Bluehost, InMotion, etc.

```
Requirements:
├── PHP 7.4+ with mail() enabled
├── MySQL 5.7+ or MariaDB 10.3+
└── mod_rewrite (for clean URLs)
```

For WhatsApp integration, no API key is needed — it uses the `wa.me/` redirect URL.

---

<details>
<summary><strong>Common issues and fixes</strong></summary>

| Issue | Fix |
|---|---|
| Booking form not sending emails | Check `ADMIN_EMAIL` in config.php; some shared hosts require SMTP — swap `mail()` for PHPMailer |
| WhatsApp button not opening chat | Ensure `WHATSAPP_NUMBER` has no `+`, spaces, or dashes — just digits |
| Admin login not working | Clear browser cookies; default credentials are in `includes/config.php` |
| Images not loading after deploy | Check file permissions — images folder should be `755`, files `644` |
| Map not showing | Google Maps Embed API key must have the `Maps Embed API` product enabled |

</details>

---

<div align="center">

Built by [Harish K](https://github.com/harryatwork)

</div>