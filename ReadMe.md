
# Welcome to the React Boot Camp

## HTML

## CSS

## JavaScript

## React

### Create a React project for JavaScript

To create a React project using Vite and JavaScript, follow these steps.

### 1. Run the Vite Initializer
Open your terminal (or command prompt) and run the following command:

```bash
npm create vite@latest my-react-app
```
*(Replace `my-react-app` with whatever name you want for your folder.)*

---

### 2. Select the Options
After running the command, you will be prompted to select your settings using your arrow keys:

1.  **Select a framework:** Use arrows to select **React** and press Enter.
2.  **Select a variant:** Use arrows to select **JavaScript** (or **JavaScript + SWC** for a faster compiler) and press Enter.

---

### 3. Install Dependencies
Vite creates the project structure but does not install the packages automatically. Navigate into your folder and install them:

```bash
cd my-react-app
npm install
```

---

### 4. Start the Development Server
Once the installation is finished, start the local server:

```bash
npm run dev
```

The terminal will provide a URL (usually `http://localhost:5173`). Open this in your browser to see your new React app running.

---

### Folder Structure Overview
Once created, your project will look like this:
*   **`index.html`**: The entry point (located in the root folder, unlike Create React App).
*   **`src/main.jsx`**: The JavaScript entry point that renders the React app.
*   **`src/App.jsx`**: Your main React component.
*   **`vite.config.js`**: The configuration file for Vite.

### Common Commands
*   **`npm run dev`**: Starts the local development server.
*   **`npm run build`**: Creates a production-ready `dist` folder.
*   **`npm run preview`**: Lets you view the production build locally.

### Why use Vite instead of Create React App (CRA)?
1.  **Speed:** Vite uses native ES Modules and an extremely fast bundler (esbuild), making the server start almost instantly.
2.  **HMR (Hot Module Replacement):** Updates to your code show up in the browser nearly instantly, regardless of project size.
3.  **Modern Tooling:** It is the current industry standard for React development.

### Create a React project for TypeScript

Creating a **TypeScript** React project with Vite is very similar to the JavaScript process, but you select different options during the setup.

### 1. Run the Initializer
Open your terminal and run:

```bash
npm create vite@latest my-ts-react-app
```

---

### 2. Select TypeScript Options
Follow the interactive prompts:

1.  **Select a framework:** Use arrows to select **React** and press Enter.
2.  **Select a variant:** Use arrows to select **TypeScript** or **TypeScript + SWC**.
    *   *Note: **SWC** (Speedy Web Compiler) is a super-fast Rust-based compiler. It is highly recommended for the best performance.*

---

### 3. Install and Run
Navigate into your project folder, install the dependencies, and start the server:

```bash
cd my-ts-react-app
npm install
npm run dev
```

---

### The "One-Liner" (Shortcut)
If you want to skip the interactive menus and create the project immediately, run this command:

```bash
# For npm
npm create vite@latest my-ts-react-app -- --template react-ts

# For Yarn
yarn create vite my-ts-react-app --template react-ts
```

---

### Key Differences in a TypeScript Project
When you choose the TypeScript template, Vite sets up a few extra things for you:

1.  **File Extensions:** Instead of `.js` and `.jsx`, your files will use **`.ts`** (for logic) and **`.tsx`** (for components).
2.  **`tsconfig.json`**: This file contains the configuration for the TypeScript compiler. Vite usually creates two: `tsconfig.json` and `tsconfig.node.json`.
3.  **`vite-env.d.ts`**: A declaration file that helps TypeScript understand Vite-specific features like importing CSS modules or environment variables.
4.  **Type Checking:** By default, Vite does **not** perform type checking during the development build (for speed). To check for type errors, you usually run `npm run build` or use an IDE like VS Code with the "TypeScript Vue Plugin" or built-in TS support.

### Recommended: Adding a Type-Check Script
Since Vite's dev server only handles transpilation (converting TS to JS) and not type-checking, most developers add a "check" script to their `package.json`:

```json
"scripts": {
  "type-check": "tsc --noEmit"
}
```
You can run `npm run type-check` before committing code to ensure there are no TypeScript errors.


