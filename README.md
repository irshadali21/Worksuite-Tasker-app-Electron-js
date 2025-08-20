# Worksuite Tasker Desktop App

Worksuite Tasker is a desktop time tracking application built with [Electron](https://www.electronjs.org/). It interacts with the Worksuite backend so users can log their work hours and automatically capture screenshots during a session.

## Features

- Secure login with email/password and token storage using **electron-store**.
- Dashboard displays current time and lets users clock in or clock out.
- Project and task selectors with the option to create new tasks.
- Start and stop timelogs with a live elapsed-time timer.
- Periodic screenshots captured via Electron and uploaded to Backblaze S3.
- Idle detection with automatic stop and optional auto-restart of timelogs.
- Configurable screenshot interval and idle timeout fetched from the backend.
- Toast notifications for success, warning, and error messages.

## User Interface

- **Login Screen:** Styled form with email and password fields plus a loading spinner while authentication is in progress.
- **Dashboard:** Welcome card with the user's name and a real-time clock alongside clock-in and clock-out buttons. The “Start Your Task” section provides project and task dropdowns, an optional new task input, start/stop buttons, and an active timer display.

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
