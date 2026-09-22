# Creating a Laravel Project — Step by Step

## 1. Check the prerequisites
Make sure PHP, Composer, Node.js, and npm are installed and available on your system PATH.

Check the installed versions:
```
php --version
composer --version
node --version
npm --version
```

## 2. Create the Laravel project
Create a new project with Composer:
```
composer create-project laravel/laravel <project-name>
```

Move into the project folder:
```
cd <project-name>
```

Alternatively, if the Laravel installer is installed:
```
laravel new <project-name>
cd <project-name>
```

## 3. Configure the environment
Laravel includes an `.env` file for local configuration. Open it and update the application and database settings as needed.

Generate the application key if it has not already been generated:
```
php artisan key:generate
```

## 4. Set up the database
- Create a database using MySQL, PostgreSQL, SQLite, or another supported database.
- Update `DB_CONNECTION`, `DB_DATABASE`, `DB_USERNAME`, and `DB_PASSWORD` in `.env`.
- For SQLite, create the database file if needed and set `DB_CONNECTION=sqlite`.

## 5. Run the migrations
Create the default database tables:
```
php artisan migrate
```

If the project includes seeders, also add sample data:
```
php artisan migrate --seed
```

## 6. Install frontend dependencies
```
npm install
```

Build the frontend assets during development:
```
npm run dev
```

For a production build:
```
npm run build
```

## 7. Link storage
Run this if the application stores public files or user uploads:
```
php artisan storage:link
```

## 8. Run the project
Start the Laravel development server:
```
php artisan serve
```

Open the URL shown in the terminal, usually:
```
http://127.0.0.1:8000
```

For projects that define a combined development script, you can run:
```
composer run dev
```

---

### Troubleshooting tips
- If PHP, Composer, Node.js, or npm commands aren't recognized, add their installation folders to your system PATH.
- If the application key is missing, run `php artisan key:generate`.
- If database errors occur, check the database service and the connection values in `.env`.
- If cached configuration causes unexpected behavior, clear the caches:
	```
	php artisan config:clear
	php artisan cache:clear
	php artisan view:clear
	```
- Check `composer.json` and `package.json` for project-specific commands.
