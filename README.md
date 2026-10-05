# Todo App - Task Management Application
### Overview

<p>Welcome to the Todo App, a responsive task management application that helps users organize their daily activities. The project is built with a focus on clean architecture, type safety and a smooth user experience. It supports the complete todo workflow (create, edit, complete, filter and delete tasks) and synchronizes every change with a remote REST API, so the data is preserved between sessions. </p>

<p>The interface and interaction patterns are based on the TodoMVC application and extended with server communication, per-task loading indicators and error notifications.</p>

### Demo

You can view a live demo of the application: [LIVE DEMO](https://mate-academy.github.io/react_todo-app/)

### Key Features
<ul>
<li>Todo Management: Create, edit, complete and delete tasks.</li>
<li> Status Filters: Display all, active or completed todos without reloading the page.</li>
<li> Bulk Actions: Toggle the status of all tasks at once or remove all completed tasks with a single click.</li>
<li>Active Task Counter: See how many todos are still incomplete.</li>
<li>API Synchronization: Persist every change (add, update, delete) through a REST API.</li>
<li>Loading States: A loader is shown only on the task that is being processed, while the rest of the interface stays usable.</li>
<li>Error Handling: Clear notifications are displayed when an API request fails, and the list keeps its previous valid state.</li>
<li>Smooth Transitions: Animated appearance and removal of list items.</li>
<li>Responsive Layout: The application works comfortably on desktop and mobile screens.</li>
</ul>
<p></p>

### Challenges

<p>Developing the application involved several challenges, particularly around asynchronous logic and keeping the interface consistent with the server.</p>

### Key Challenges
<ul>
<li>Asynchronous State Management: Several requests can be in flight at the same time (for example, when all tasks are toggled at once). The application has to know which tasks are being processed and update only them when the responses arrive.</li>
<li>UI and Server Consistency: The local state must always reflect what the server has actually accepted, so changes are applied after a successful response and the previous state is kept when a request fails.</li>
<li>Error Handling: Network errors and failed operations are shown to the user through a clear notification instead of failing silently.</li>
<li>Bulk Operations: Toggling or clearing many tasks means sending several requests in parallel and correctly handling partial failures.</li>
<li> Type Safety: Describing API responses, component props and filter values with TypeScript interfaces and enums prevents a whole class of runtime bugs.</li>
<li> Responsive Design: The layout has to stay readable and convenient on screens of very different sizes.</li>
<li> Code Quality: Keeping a consistent code style across TypeScript and SCSS files required a strict linting and formatting setup.</li>
</ul>
<p>These challenges were addressed through careful component decomposition, typed models, a dedicated API layer and iterative testing.</p>

### Installation & Setup

<p> To install the project and run it locally, follow these steps:</p>
<ol>
<li>Clone the repository:
   git clone https://github.com/maximtsyrulnyk/react_todo-app_new.git</li>
<li> Navigate to the project directory:
   cd react_todo-app_new</li>
<li> Install dependencies:
   npm install</li>
<li> Start the local development server:
   npm start</li>
<li>Build & deploy: </li>
   npm run build
   npm run deploy
</ol>
Requirements: Node.js 20 and npm.

### Available Scripts
<ul>
 <li>npm start - runs the development server.</li>
<li> npm run build - creates an optimized production build.</li>
<li> npm run lint - formats and lints TypeScript and SCSS files.</li>
<li> npm run format - formats TypeScript files with Prettier.</li>
<li> npm run lint-js - lints JavaScript and TypeScript code with ESLint.</li>
<li> npm run lint-css - lints SCSS styles with Stylelint.</li>
<li> npm run deploy - builds the project and publishes it to GitHub Pages.</li>
</ul>

### Technologies Used
### Core
<ol>
<li> React 18.3.1: For building the component-based user interface. </li>
<li> TypeScript 5.2.2: For static typing and a safer development experience.</li>
<li> SCSS (Sass 1.77.8): For modular and maintainable styling.</li>
</ol>

### UI
<ol>
<li>Bulma 1.0.1: For ready-made, reusable interface styles.</li>
<li> Font Awesome 6.5.2: For interface icons.</li>
<li>Classnames 2.5.1: For conditional CSS class management.</li>
<li>React Transition Group 4.4.5: For animated transitions of list items.</li>
<li>React Router DOM 6.25.1: For routing and navigation between filters.</li>
</ol>

### Data
Fetch API: For communication with the server.
REST API: For remote todo storage and CRUD operations.
### Development and Deployment
Vite 5.3.1: For a fast development server and optimized production builds.
Cypress 13.13.0: For end-to-end testing infrastructure.
ESLint, Stylelint and Prettier: For code quality and consistent formatting.
gh-pages 6.1.1: For publishing the build to GitHub Pages.
### Project Structure
public/ - static assets.
src/ - application source code (components, types, styles and API logic).
index.html - application entry HTML file.
vite.config.ts - Vite configuration.
tsconfig.json - TypeScript configuration.
.eslintrc.cjs, .stylelintrc.js, .prettierrc - linting and formatting rules.
LICENSE - GPL-3.0 license text.
### How It Works
A user performs an action, for example ticks a checkbox next to a task.
The task is marked as "processing", so only this item displays a loader.
A request is sent to the REST API.
On success, the local state is updated with the server response.
On failure, an error notification is shown and the previous state is preserved.
The task is removed from the "processing" list in both cases.

### License

<p>This project is distributed under the GPL-3.0 license. See the LICENSE file for details.</p>
