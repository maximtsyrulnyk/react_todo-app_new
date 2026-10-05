# Final Review: React
## Getting Started

Follow these steps to run the project locally.

1. Clone the repository and enter the project directory:

   ```bash
   git clone https://github.com/maximtsyrulnyk/react_todo-app_new.git
   cd todo-app-portfolio
   ```

2. Install the dependencies:

   ```bash
   npm install
   ```

3. Start the development server:

   ```bash
   npm start
   ```

## Features

- **Todo management:** Create, edit, complete, and delete tasks.
- **Status filters:** Display all, active, or completed todos.
- **Bulk actions:** Toggle all tasks or remove all completed tasks at once.
- **Active task counter:** See how many todos are still incomplete.
- **API synchronization:** Persist all changes through a REST API.
- **Loading states:** Track pending operations for individual tasks.
- **Error handling:** Display clear notifications when an API request fails.
- **Responsive layout:** Use the application on desktop and mobile screens.


### upd
<h1>Todo Manager — React + TypeScript</h1>
<p>A single-page task manager built with React and TypeScript. Users can plan their day, track progress and keep everything in sync with a remote REST API. The interface adapts to phones, tablets and desktops.</p>

[Live demo](github.com/maximtsyrulnyk/react_todo-app_new.git) → · Report a bug
---
Table of contents
Overview
Key features
Tech stack
Quick start
Available scripts
Project structure
How data flows
Testing and code quality
Deployment
Roadmap
Acknowledgements
License
---
Overview
The app covers the full lifecycle of a task: create it, rename it, mark it as done and remove it when it is no longer needed. Every action is sent to a backend over HTTP, so the list survives page reloads. While a request is in flight, the affected task shows a loading state, and if the request fails the user sees an error message instead of a silent failure.
The UX follows the well-known TodoMVC specification, which made it a good base for practising state management, async logic and end-to-end testing.
Key features
Area	What you get
Task CRUD	Add a task, edit its title in place, toggle completion, delete it
Filtering	Switch between All, Active and Completed views
Batch operations	Mark every task as done (or undo it) in one click; clear all completed tasks at once
Counter	Live count of tasks that are still unfinished
Server sync	All changes are persisted through a REST API
Per-task loading	Only the task being processed is blocked, the rest of the UI stays usable
Error feedback	A dismissible notification appears when a request fails
Responsive UI	Layout works on both small and large screens
Tech stack
Front end
React 18.3.1 — component-based UI
TypeScript 5.2.2 — static typing
SCSS 1.77.8 — modular styles
Bulma 1.0.1 — ready-made CSS components
Font Awesome 6.5.2 — icons
classnames 2.5.1 — conditional class composition
Networking
Native `fetch` wrapped in a small API client
Remote REST API for storing todos
Tooling
Vite 5.3.1 — dev server and bundler
Cypress 13.13.0 — end-to-end tests
ESLint, Stylelint, Prettier — linting and formatting
GitHub Pages — hosting
> Versions match `package.json` at the time of writing. If you upgrade dependencies, update this list too.
Quick start
Requirements: Node.js 18+ and npm.
```bash
# 1. Get the code
git clone https://github.com/maximtsyrulnyk/react_todo-app_new.git
cd react_todo-app_new

# 2. Install dependencies
npm install

# 3. Run the dev server
npm start
```
The app opens at `http://localhost:5173` (Vite default; the port may differ if it is busy).
Available scripts
Command	Purpose
`npm start`	Run the development server with hot reload
`npm run build`	Create an optimised production build in `dist/`
`npm run lint`	Check the code with ESLint and Stylelint
`npm run test`	Open Cypress and run end-to-end tests
`npm run deploy`	Publish the build to GitHub Pages
> Script names may differ slightly in your `package.json` — adjust the table if needed.
Project structure
```text
src/
├── api/          # HTTP helpers and todo requests
├── components/   # Presentational and container components
├── types/        # Shared TypeScript interfaces and enums
├── utils/        # Pure helper functions (filtering, etc.)
├── styles/       # Global and partial SCSS files
├── App.tsx       # Root component and top-level state
└── index.tsx     # Application entry point
cypress/          # E2E specs and fixtures
```
How data flows
A user action (for example, ticking a checkbox) triggers a handler in the root component.
The task ID is added to a "processing" list, so only that item shows a spinner.
The API client sends the request to the server.
On success, local state is updated with the server response.
On failure, an error message is shown and the previous state is kept.
The task ID is removed from the "processing" list in all cases.
This approach keeps the UI honest: what the user sees always reflects what the server has actually accepted.
Testing and code quality
End-to-end tests with Cypress cover the main user scenarios: adding, editing, toggling, filtering and deleting tasks, plus error handling.
Static analysis is handled by ESLint (logic), Stylelint (SCSS) and Prettier (formatting).
Run `npm run lint` before every commit to keep the codebase consistent.
Deployment
The production build is published to GitHub Pages. To deploy manually:
```bash
npm run build
npm run deploy
```
Make sure the `base` option in `vite.config.ts` matches the repository name, otherwise assets will not load.
Roadmap
<ol>
<li> [ ] Drag-and-drop reordering </li>
<li> [ ] Due dates and priorities </li>
<li> [ ] Optimistic UI updates </li>
<li> [ ] Unit tests for helpers and the API layer</li >
<li> [ ] Dark theme</li>
</ol>

## Acknowledgements
The interaction model and visual style are inspired by TodoMVC. Icons are provided by Font Awesome.
## License
Distributed under the GPL-3.0 license. See the LICENSE file for details.
