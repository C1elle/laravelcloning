# Web Development Notes

This folder contains personal web development notes and step-by-step guides for creating, cloning, configuring, and running Laravel and Next.js projects. It is a quick reference for common setup commands, environment configuration, databases, dependencies, and troubleshooting.

## Contents

- [Create a Laravel project](creatinglaravelproject.md)
- [Clone and run a Laravel project](cloninglaravel.md)
- [Create a Next.js project](creatingnextjs.md)

## Quick Reference

### Laravel

Create a new Laravel application:

```bash
composer create-project laravel/laravel <project-name>
cd <project-name>
php artisan key:generate
php artisan migrate
npm install
npm run dev
php artisan serve
```

Clone an existing Laravel application:

```bash
git clone <your-fork-url>
cd <project-folder>
composer install
npm install
```

Then configure `.env`, generate the application key, run migrations, and start the development server.

### Next.js

Create a new Next.js application with the official generator:

```bash
npx create-next-app@latest <project-name>
cd <project-name>
npm run dev
```

The default development server is usually available at `http://localhost:3000`.

## Prerequisites

Install the tools required by the project you are working on:

- Git
- PHP and Composer for Laravel
- Node.js and npm for Laravel frontend assets and Next.js
- A supported database for Laravel applications
- Visual Studio Code or another code editor

Check installed versions with:

```bash
php --version
composer --version
node --version
npm --version
git --version
```

## Environment and Security

- Keep local secrets in `.env` or `.env.local`.
- Do not commit environment files containing passwords, API keys, or other secrets.
- Use `NEXT_PUBLIC_` only for Next.js values that are safe to expose in the browser.
- Check each project's `composer.json` and `package.json` for project-specific scripts.

## Troubleshooting

- If a command is not recognized, verify that the relevant tool is installed and available on your system `PATH`.
- For Laravel database errors, check that the database service is running and that the `.env` connection values are correct.
- For Laravel configuration issues, clear cached configuration with `php artisan config:clear`.
- If the Next.js development port is busy, run `npm run dev -- --port 3001`.

## Contributing

Add clear, reproducible notes as new Markdown files and link them from this README. Keep commands tested, platform differences explicit, and secrets out of the repository.
