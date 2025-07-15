# Worksuite Tasker Desktop/Mac App

Worksuite Tasker is a time tracking application built with [Electron](https://www.electronjs.org/). It interacts with the Worksuite backend so users can log their work hours and automatically capture screenshots during a session.

## Features

- Login and token storage using **electron-store**.
- Dashboard for starting and stopping timelogs.
- Periodic screenshots uploaded to S3 type storage.
- Idle detection to automatically stop a running timelog.
- Fetches projects and tasks from Worksuite APIs.

Features like screenshot and stop a running timelog was a request by the client 

## Requirements

- [Node.js](https://nodejs.org/) (version 16 or later recommended)
- npm

## Installation

```bash
npm install
```

## Running in Development

Launch the app with Electron:

```bash
npm start
```

## Building Distributables

To create a packaged application use:

```bash
npm run dist
```

## Repository Structure

- `main.js` – Main process code that creates windows and handles screenshot IPC events.
- `renderer/` – Renderer process pages and scripts such as the dashboard and login screens.
- `Login/` – Static assets for the login screen.
- `utils/api.js` – Axios instance that communicates with the Worksuite backend.

The application checks for a stored user token at start up and either loads the login screen or the dashboard accordingly.

---

This project does not currently include automated tests. Running `npm test` will show an error because the `test` script is not defined.
