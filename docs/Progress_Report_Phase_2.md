# Meaningful Logs and Progress Report

Date: March 24, 2026
Repository: `https://github.com/Tunify-T8/Sound_Cloud_Clone-Team8.git`

## Purpose

This document summarizes:

- meaningful activity in the Git repository
- the confirmed project management and collaboration tooling
- the main development tools used across backend, frontend, and mobile
- a progress report as of March 24, 2026

## Repository Snapshot

- Default branch: `main`
- Remote tracked: `origin/main`
- Total commits on `HEAD`: `111`
- First commit in this repository: on March 19, 2026
- Latest commit at time of review: on March 24, 2026



### Repository milestones

The following commits tell the clearest story of project progress:

| Date | Commit | Type | Meaning |
| --- | --- | --- | --- |
| 2026-03-19 | `5ba7ab5` | bootstrap | Initial commit created the repository baseline. |
| 2026-03-19 | `1b17e78` | platform setup | Added Docker Compose for development and production, introduced a CD workflow, and added a messages page. |
| 2026-03-19 | `8a6c4dd` | infrastructure | Set up Caddy reverse proxy for HTTPS. |
| 2026-03-19 | `3e46c0d` | backend config | Injected email credentials for Nodemailer. |
| 2026-03-19 | `3090d3f` | secrets management | Added `BACKEND_ENV_VARS` for dynamic secret injection. |
| 2026-03-20 | `9d61f2a` | reliability | Added database health checks to avoid backend crash loops. |
| 2026-03-20 | `4332fee` | deployment fix | Moved frontend and backend behind one domain with `/api/*` path-based routing. |
| 2026-03-22 | `31da75d` | background jobs | Added persistent Redis 7 container for Bull-based background processing. |
| 2026-03-22 | `b2a8024` | media pipeline | Added FFmpeg installation to support audio processing workflows. |
| 2026-03-22 | `eaefdc8` | database ops | Upgraded PostgreSQL image to `16-alpine`. |
| 2026-03-23 | `10bf9a3` | auth/deploy config | Added Google redirect URI build argument for deployment. |
| 2026-03-23 | `831cb38` | environment config | Added environment variable support for deployment/runtime configuration. |

### Automation pattern visible in history

- This repository is being updated by automation.
- This is an integration repository that receives backend and frontend snapshots from other commit SHAs. This is an inference from commit history, not from a visible sync workflow file in this repo.


## Project Management and Collaboration Tools



- GitHub is serving as the source-control platform and release automation surface.
- A lightweight workflow centered on pushes to `main` is in use.
- Continuous delivery is configured to build images, push them to Docker Hub, and deploy them to  Azure VM.


### Source control, CI/CD, and deployment

- Git
- GitHub
- GitHub Actions
- Docker
- Docker Compose
- Docker Hub
- Azure VM deployment
- Caddy reverse proxy

### Backend stack

- NestJS
- Prisma ORM
- PostgreSQL
- Redis
- Bull queue integration
- Passport authentication strategies
- JWT auth
- Nodemailer
- FFmpeg and FFprobe
- Jest
- ESLint
- Prettier
- TypeScript

### Frontend stack

- React 19
- Vite
- TypeScript
- React Router
- Redux Toolkit
- TanStack Query
- Tailwind CSS 4
- Vitest
- Testing Library
- JSON Server for mock APIs

### Mobile stack

- Flutter
- Riverpod
- Dio
- Flutter Secure Storage
- Google Sign-In
- Just Audio
- Image Picker
- File Picker
- Mockito
- Build Runner

## Progress Report

### Overall status



### Completed or strongly established areas

- Monorepo-style structure covering `backend`, `frontend`, and `mobile`
- Automated CD pipeline on pushes to `main`
- Containerized development and production environments
- HTTPS reverse proxy and single-domain routing strategy
- Backend module 1 ,2 and 4
- Frontend module 1 ,2 and 4 
- Cross module 1 , 2 and 4
- Oath not completed yet 
- Some minor bug fixes and UI changes are needed
- E2E testing not done yet



### Current delivery assessment by surface

#### Backend

Progress is strong. The backend has a cohesive module layout and operational support for database access, auth, storage, audio handling, and queue-backed work.

#### Frontend

Progress is weaker than backend, alot of UI changes are needed
#### Mobile

Progress is broad and  the most feature-complete by structure and tests. The mobile app contains dedicated domains for auth, upload/management, feed/discovery, messaging, notifications, profile, playlists, premium subscription, playback, and social interactions.

### Risks and gaps

- Repository history is dominated by bot sync commits


### Recommended next documentation steps

- Expand the root `README.md` with setup, architecture, and deployment notes.
- Add a short contribution guide describing how frontend/backend sync automation works.
- Standardize commit messages to improve future progress reporting.
- Add a release log or sprint log if this repository is being used for stakeholder reporting.

