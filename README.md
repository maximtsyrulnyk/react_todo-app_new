<h1 align="center">📝 React Todo App</h1>
<p align="center">
  A responsive task manager built with <b>React</b>, <b>TypeScript</b> and <b>SCSS</b>,<br/>
  fully synchronised with a <b>REST API</b> and covered by <b>end-to-end tests</b>.
</p>

  [TODO app](https://mate-academy.github.io/react_todo-app/)
  <img src="https://img.shields.io/badge/React-18.3-61DAFB?style=for-the-badge&logo=react&logoColor=white" alt="React"/>
  <img src="https://img.shields.io/badge/TypeScript-5.2-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Vite-5.3-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite"/>
  <img src="https://img.shields.io/badge/Cypress-13.13-17202C?style=for-the-badge&logo=cypress&logoColor=white" alt="Cypress"/>
  <img src="https://img.shields.io/badge/license-GPL--3.0-blue?style=for-the-badge" alt="License"/>

---
📑 Table of Contents
Overview
Demo
Screenshots
Key Features
Challenges
Installation & Setup
Available Scripts
Technologies Used
Project Structure
How It Works
Testing & Code Quality
Roadmap
Acknowledgements
License
---
🔎 Overview
Welcome to the React Todo App — a task management application created to help users plan their day and keep track of progress. The project follows the interaction model of TodoMVC and extends it with real server communication, per-task loading indicators, error notifications and a fully responsive layout.
The application covers the complete life cycle of a task: creating, renaming, completing, filtering and deleting. Every action is persisted through a REST API, so the list is preserved between sessions and devices. The code is written in TypeScript with strict typing, styled with modular SCSS on top of the Bulma framework, and verified with Cypress end-to-end tests.
This project was built to practise:
component-based architecture and state management in React;
asynchronous logic and communication with a remote API;
user-friendly handling of loading and error states;
writing maintainable, typed and tested front-end code.
🚀 Demo
You can view a live version of the application here: DEMO
> ℹ️ If the page shows a 404, the deployment may not be published yet. See the [Deployment](#-available-scripts) notes below.
🖼 Screenshots
Desktop	Mobile
![Desktop view](./docs/screenshot-desktop.png)	![Mobile view](./docs/screenshot-mobile.png)
> Add your own screenshots to the `docs/` folder and keep the file names above (or update the paths).
✨ Key Features
Task Management: Create, edit (double-click to rename), complete and delete tasks.
Status Filters: Switch between All, Active and Completed views without reloading the page.
Bulk Actions: Toggle every task at once with a single control, or remove all completed tasks in one click.
Active Task Counter: A live counter shows how many tasks are still unfinished.
API Synchronisation: All changes (add, update, delete) are stored on the server through REST requests.
Per-Task Loading States: A loader is displayed only on the task being processed, while the rest of the interface stays usable.
Error Handling: A dismissible notification explains what went wrong when a request fails; the previous state of the list is preserved.
Inline Editing: Save the new title with Enter or on blur, cancel with Escape; empty titles delete the task.
Responsive Layout: Comfortable usage on phones, tablets and desktops.
Accessible Controls: Semantic HTML, focus management and keyboard support for the main actions.
🧗 Challenges
Building the application involved several non-trivial problems that go beyond a basic CRUD list.
Key Challenges
Asynchronous State Management: Several requests can be in flight at the same time (for example, toggling many tasks at once). The UI must know which tasks are being processed and update only them when responses arrive.
Consistency Between UI and Server: Local state must always reflect what the server has actually accepted, so changes are applied only after a successful response and rolled back or kept unchanged on failure.
Error Handling: Network errors, empty titles and failed deletions are shown to the user through a clear, auto-hiding notification instead of failing silently.
Inline Editing UX: Handling Enter, Escape, blur and empty values consistently required careful event management and focus control.
Bulk Operations: Toggling or clearing many tasks means sending several requests in parallel and correctly handling partial failures.
Type Safety: Describing API responses, component props and filter states with TypeScript interfaces and enums prevented a whole class of runtime bugs.
Responsive Design: The interface had to stay readable and convenient across very different screen sizes.
Testing: Covering real user scenarios with Cypress (including mocked API failures) required stable selectors and predictable loading states.
These challenges were solved through careful component decomposition, a dedicated API layer, typed models and iterative testing.
⚙️ Installation & Setup
Requirements: Node.js 18+ and npm.
To install the project and run it locally, follow these steps:
Clone the repository:
```bash
   git clone https://github.com/maximtsyrulnyk/react_todo-app_new.git
   ```
Navigate to the project directory:
```bash
   cd react_todo-app_new
   ```
Install dependencies:
```bash
   npm install
   ```
Start the local development server:
```bash
   npm start
   ```
The app will be available at `http://localhost:5173` (the port may differ if it is already in use).
Build & deploy:
```bash
   npm run build
   npm run deploy
   ```
📜 Available Scripts
Command	Description
`npm start`	Runs the development server with hot module replacement
`npm run build`	Creates an optimised production build in the `dist/` folder
`npm run preview`	Serves the production build locally for a final check
`npm run lint`	Checks the code with ESLint and Stylelint
`npm run test`	Opens Cypress for end-to-end testing
`npm run deploy`	Publishes the production build to GitHub Pages
> Script names depend on your `package.json`. Adjust this table if some commands differ.
Deployment notes (GitHub Pages)
If the demo link returns a 404, check the following:
In Settings → Pages, the source is set to the `gh-pages` branch (or GitHub Actions), and the site is published.
`vite.config.ts` contains `base: '/react_todo-app_new/'` — it must match the repository name exactly.
`npm run deploy` finished without errors and the `gh-pages` branch exists on GitHub.
The repository is public (or your plan supports Pages for private repositories).
🛠 Technologies Used
Core
React 18.3.1: For building the component-based user interface.
TypeScript 5.2.2: For static typing, safer refactoring and a better development experience.
SCSS 1.77.8: For modular, maintainable and reusable styles.
UI
Bulma 1.0.1: For ready-made, responsive interface components.
Font Awesome 6.5.2: For interface icons.
classnames 2.5.1: For conditional CSS class composition.
Data
Fetch API: For communication with the server.
REST API: For remote storage and CRUD operations on todos.
Tooling & Quality
Vite 5.3.1: For a fast dev server and optimised production builds.
Cypress 13.13.0: For end-to-end testing of user scenarios.
ESLint: For linting JavaScript and TypeScript code.
Stylelint: For linting SCSS styles.
Prettier: For consistent code formatting.
GitHub Pages: For hosting and deployment.
> Versions correspond to `package.json` at the time of writing — update them after upgrading dependencies.
🗂 Project Structure
```text
react_todo-app_new/
├── cypress/              # E2E specs, fixtures and support files
├── docs/                 # Screenshots used in this README
├── public/               # Static assets
├── src/
│   ├── api/              # HTTP client and todo requests
│   ├── components/       # UI components (header, list, item, footer, notifications)
│   ├── types/            # Shared TypeScript interfaces and enums
│   ├── utils/            # Pure helpers (filtering, counters)
│   ├── styles/           # Global and partial SCSS files
│   ├── App.tsx           # Root component and top-level state
│   └── index.tsx         # Application entry point
├── .eslintrc / .stylelintrc / .prettierrc
├── vite.config.ts
├── tsconfig.json
└── package.json
```
> Update the tree so it matches the actual folders in your repository.
🔄 How It Works
The diagram below shows what happens when a user changes a task:
```text
User action ──► Handler in App ──► Mark task as "processing"
                                         │
                                         ▼
                                  API request (fetch)
                              ┌──────────┴──────────┐
                           success                failure
                              │                      │
                              ▼                      ▼
                    Update local state       Show error notification
                              └──────────┬──────────┘
                                         ▼
                           Remove task from "processing"
```
Key ideas:
The list of tasks is the single source of truth in the root component and is passed down through props.
A separate collection of "processing" IDs controls which tasks display a loader.
Filtering and counters are derived from the task list, so they never get out of sync.
All network code is isolated in the `api/` folder, which keeps components free of request details.
✅ Testing & Code Quality
End-to-end tests (Cypress) simulate real user behaviour: adding, editing, toggling, filtering, deleting tasks and handling API errors.
ESLint + Stylelint catch potential bugs and style issues before they reach the repository.
Prettier keeps the formatting consistent across the whole codebase.
Run the checks locally:
```bash
npm run lint
npm run test
```
🗺 Roadmap
[ ] Drag-and-drop reordering of tasks
[ ] Due dates and priorities
[ ] Optimistic UI updates with rollback
[ ] Dark / light theme switcher
[ ] Unit tests for helpers and the API layer
[ ] Search by task title
🙏 Acknowledgements
The interface and interaction patterns are based on the TodoMVC specification.
Icons are provided by Font Awesome.
UI components are provided by Bulma.
📄 License
This project is distributed under the GPL-3.0 license. See the LICENSE file for details.
---
<p align="center">Made with ❤️ by <a href="https://github.com/maximtsyrulnyk">maximtsyrulnyk</a></p>
