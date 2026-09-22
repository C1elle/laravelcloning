# Creating a Next.js Project — Step by Step

## 1. Check the prerequisites
Make sure Node.js and npm are installed and available on your system PATH.

Check the installed versions:
```
node --version
npm --version
```

Use a current Node.js LTS version. Next.js may not support every older Node.js version.

## 2. Create the Next.js project
Run the official project generator:
```
npx create-next-app@latest <project-name>
```

Answer the setup questions. A good general-purpose setup is:
- TypeScript: Yes
- ESLint: Yes
- Tailwind CSS: Yes, if the project needs it
- `src/` directory: Yes
- App Router: Yes
- Turbopack: Yes, if offered and supported by the project
- Customize the import alias: No, unless the project needs a different alias

Move into the project folder:
```
cd <project-name>
```

You can also pass options directly. For example:
```
npx create-next-app@latest <project-name> --typescript --eslint --tailwind --src-dir --app
```

## 3. Open the project in your editor
If you use Visual Studio Code, open the project folder:
```
code .
```

The main application code is usually inside:
```
src/app
```

Important files and folders include:
- `src/app/page.tsx`: the home page
- `src/app/layout.tsx`: the shared root layout
- `public`: static files such as images and icons
- `.env.local`: local environment variables
- `package.json`: dependencies and project scripts

## 4. Configure environment variables
Create a `.env.local` file in the project root when the application needs local configuration:
```
API_URL=http://localhost:8000
NEXT_PUBLIC_APP_NAME=My Next.js App
```

Use variables beginning with `NEXT_PUBLIC_` only for values that are safe to expose in the browser. Keep private keys and secrets without that prefix.

Do not commit `.env.local` or other files containing secrets. The generated project normally includes these files in `.gitignore`.

## 5. Start the development server
Run the development server from the project folder:
```
npm run dev
```

Open the URL shown in the terminal, usually:
```
http://localhost:3000
```

Edit `src/app/page.tsx` and save the file. The browser should update automatically.

## 6. Add dependencies when needed
Install a package with npm:
```
npm install <package-name>
```

Install a development-only package with:
```
npm install --save-dev <package-name>
```

For example, to add the official React type packages to a project that needs them:
```
npm install -D @types/node @types/react @types/react-dom
```

## 7. Check the project before sharing it
Run the linter:
```
npm run lint
```

Create a production build:
```
npm run build
```

Start the production build locally:
```
npm run start
```

Stop the development or production server with `Ctrl+C` in the terminal.

## 8. Initialize Git (optional)
If the project is not already a Git repository:
```
git init
git add .
git commit -m "Create Next.js project"
```

Create a repository on GitHub and connect it to the local project as needed:
```
git remote add origin <repository-url>
git branch -M main
git push -u origin main
```

---

### Troubleshooting tips
- If `npx` or `npm` is not recognized, install Node.js LTS and make sure its installation folder is on your system PATH.
- If the port is already in use, start Next.js on another port:
	```
	npm run dev -- --port 3001
	```
- If dependencies are out of sync, remove `node_modules` and the lock file, then run `npm install` again. Keep the lock file used by the project when committing changes.
- If an environment variable is not available in browser code, add the `NEXT_PUBLIC_` prefix and restart the development server.
- Check `package.json` for the project's available scripts and the Next.js version it uses.
