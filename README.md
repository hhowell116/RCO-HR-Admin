# RCO HR Admin Control Panel

Internal HR admin dashboard for Rowe Casa Organics — employee recognition programs, internal TV displays, and HR workflows.

**View the live demo:** [hhowell116.github.io/Demo-HR-Admin-Control-Panel](https://hhowell116.github.io/Demo-HR-Admin-Control-Panel/)

## Architecture

A monorepo with three workspace packages:

- **admin** — React admin panel for HR staff to manage content, campaigns, and permissions
- **display** — Full-screen slideshow app for Airtame-connected TVs showing employee celebrations and rockstar recognition
- **shared** — Shared types, constants, and utilities

```
Browser  →  Firebase Auth (Google SSO, @rowecasaorganics.com only)
         →  Cloud Firestore (employees, campaigns, display config, submissions)
         →  Firebase Hosting (multi-site: admin + display)
         →  Firebase Cloud Functions (user role management, data seeding)
```

## Features

- **Employee Recognition** — Birthday and work anniversary slides auto-generated from employee data
- **Rockstar Campaigns** — Monthly recognition slides with quotes, managed through the admin panel
- **TV Display** — Auto-rotating slideshow with configurable speed, progress bar, and dot navigation
- **Role-Based Access Control** — IT Admin, HR, and C-Suite roles with configurable permissions
- **Photo Submissions** — Employee self-service photo upload with QR code
- **Display Settings** — Control rotation speed, transition duration, progress bar, and dot nav
- **Guided Tour** — Onboarding walkthrough for new admin users

## Tech Stack

| Tool | Purpose |
|------|---------|
| React 18 + TypeScript | Frontend (admin + display) |
| Vite | Build tooling |
| Tailwind CSS | Styling |
| Firebase Authentication | Google SSO with domain restriction |
| Cloud Firestore | Real-time data (employees, campaigns, config) |
| Firebase Cloud Functions | User role management, data seeding |
| Firebase Hosting | Multi-site deployment (admin + display) |
| npm Workspaces | Monorepo package management |
