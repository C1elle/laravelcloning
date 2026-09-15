# Cloning a Laravel Project — Step by Step

## 1. Fork the repository
Fork the repo to your own GitHub account (if you don't have direct push access to the original).

## 2. Clone the repository
```
git clone <your-fork-url>
cd <project-folder>
```

## 3. Install PHP dependencies
```
composer install
```

## 4. Install JS dependencies (if the project uses a frontend build)
```
npm install
```

## 5. Copy the environment file
```
copy .env.example .env
```
(on Mac/Linux, use `cp .env.example .env` instead)

## 6. Generate the application key
```
php artisan key:generate
```

## 7. Set up the database
- Create the database itself (MySQL/Postgres/etc.) if it doesn't exist yet.
- Edit `.env` and set `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`, and other connection details.

## 8. Run migrations
```
php artisan migrate
```
Add sample data if the project has seeders:
```
php artisan migrate --seed
```

## 9. Link storage (if the app uses file uploads/public links)
```
php artisan storage:link
```

## 10. Build frontend assets (if applicable)
```
npm run dev
```
or for production:
```
npm run build
```

## 11. Run the project
```
composer run dev
```
or
```
php artisan serve
```

---

### Troubleshooting tips
- If Composer/PHP commands aren't recognized, make sure Composer and PHP are on your system PATH.
- If something acts strange after cloning, clear caches:
  ```
  php artisan config:clear
  php artisan cache:clear
  php artisan view:clear
  ```
- Check `composer.json` and `package.json` for project-specific scripts, since not every Laravel project uses the same stack.