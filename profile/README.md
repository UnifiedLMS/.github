<p align="center">
  <img src="./assets/unified-logo.png" alt="Unified logo" width="140" />
</p>

# Unified

Unified is an education management platform for institutions that need one system for identity, academic records, schedules, grades, and role-specific learning workflows.

The core workspace is split into a FastAPI backend and a React-based web interface. Together they provide authenticated access for administrators, teachers, and students, with operational tooling for user management, group management, schedules, assessment data, and spreadsheet-style academic workflows.


## Core Repositories

| Repository | Purpose | Stack |
| --- | --- | --- |
| `unified-api` | Backend API for authentication, users, groups, students, teachers, schedules, grades, lesson attachments, caching, and rate limiting. | Python 3.11, FastAPI, MongoDB, Redis, PyJWT, Google OAuth, Cloudinary, Docker |
| `unified-web` | Web application and local proxy server for the Unified interface. Includes admin, student, and teacher views. | React, TypeScript, Vite, Express, TanStack Query, Tailwind CSS, Radix UI, Framer Motion |

## Platform Capabilities

- Role-based authentication using password login, Google OAuth, bearer tokens, token validation, refresh, logout, and Redis-backed token revocation.
- Administrative tools for searching, updating, deleting, and listing users by role.
- Student and teacher onboarding forms with domain-specific validation.
- Group-aware schedule management with lesson creation, editing, deletion, calendar/list views, homework, topics, classrooms, and lesson metadata.
- Grade and assessment workflows, including group/discipline selection and spreadsheet import/export support.
- Student and teacher dashboards tailored to their schedules, lessons, grades, and settings.
- API protection through CORS configuration, session middleware, role-aware rate limiting, and structured request validation.
- Docker-oriented backend deployment with Nginx reverse proxy support.

## Quality Standards

- Keep API behavior documented through versioned routes and generated OpenAPI output.
- Validate request/response shapes at service boundaries with Pydantic or Zod.
- Prefer focused tests around authentication, route contracts, and high-risk academic workflows.
- Keep frontend features role-aware and consistent across admin, teacher, and student experiences.
- Avoid storing secrets in the repository; use local environment files or deployment-managed secrets.

## License

Unified is released under the MIT License. See the repository license files for details.
