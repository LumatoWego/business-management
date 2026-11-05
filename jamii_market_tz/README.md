# JAMII MARKET TZ — MVP

A PHP + MySQL multi-vendor marketplace starter project.

## Included
- Customer and seller registration/login
- Seller shop creation (shops start pending approval)
- Product upload with image validation
- Admin seller and product approval
- Public product catalogue, category filters and search
- Shopping cart and checkout
- Cash-on-delivery order records (no live payment gateway)
- Customer order history
- Reviews restricted to completed purchases

## Requirements
- PHP 8.1+ (PDO, pdo_mysql, fileinfo)
- MySQL 5.7+ or MariaDB 10.4+
- Apache/Nginx or PHP's local development server

## Installation with XAMPP
1. Place `jamii_market_tz` inside `C:\xampp\htdocs\`.
2. Start Apache and MySQL.
3. Open phpMyAdmin and import `database.sql`.
4. Copy `config.example.php` to `config.php` and set database details.
5. Visit `http://localhost/jamii_market_tz/`.
6. Register a seller account and a separate customer account.

## Create the first administrator
Register a normal account, then run this SQL in phpMyAdmin, replacing the email:

```sql
UPDATE users SET role='admin' WHERE email='your-email@example.com';
```

Log out and back in. The account page will show the Admin panel link.

## Important notes
- New shops and products require administrator approval before public listing.
- Orders currently use cash-on-delivery records only. No card, mobile-money or wallet payments are collected.
- The initial order status is `pending`. For testing, an administrator can mark an order `completed` in the database before testing verified-purchase reviews; an admin order-management UI is a future enhancement.
- Configure HTTPS, backups, production error logging, rate limiting, email verification, password reset, privacy policy, terms, and delivery/refund workflows before public launch.
- This is an MVP starter, not a production-hardened payment platform.

## Repository safety
The local `config.php` file and uploaded product images are intentionally not committed. Create your own `config.php` from `config.example.php` on your development machine. Do not commit credentials or customer data.
