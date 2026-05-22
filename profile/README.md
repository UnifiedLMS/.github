<p align="center">
  <img src="./assets/unified-bg.png" alt="Unified education platform preview" width="100%" />
</p>

# Unified

Unified is an education management platform for schools and academic teams that need one place for identity, schedules, grades, records, and role-specific workflows.

The platform combines a FastAPI service with a React web client for administrators, teachers, and students.

## Product Scope

Unified focuses on the operational core of an academic environment:

- Central user identity for admins, teachers, and students.
- Academic groups, teacher assignments, disciplines, and student profiles.
- Calendar-based lesson planning with homework, topics, classrooms, and metadata.
- Grade and assessment workflows connected to groups and disciplines.
- Spreadsheet-style import/export support for structured academic data.
- Secure access patterns for authenticated, role-specific workspaces.

## Repositories

| Repository | Role | Stack |
| --- | --- | --- |
| `unified-api` | Versioned backend for authentication, users, groups, students, teachers, schedules, grades, assessments, and lesson files. | Python, FastAPI, MongoDB, Redis, JWT, Google OAuth, Cloudinary, Docker |
| `unified-web` | Browser workspace with admin, teacher, and student views, plus a local Express proxy for API access. | React, TypeScript, Vite, Express, TanStack Query, Tailwind CSS, Radix UI |

## Core Capabilities

- Role-based access for administrators, teachers, and students.
- Password and Google OAuth authentication with token refresh and revocation.
- User, group, student, teacher, schedule, grade, and assessment workflows.
- Student and teacher dashboards for lessons, calendars, grades, and settings.
- Spreadsheet-oriented academic data handling.
- Redis-backed caching and rate limiting.
- Docker-ready API deployment with Nginx support.

## Role Workflows

| Role | Primary workflows |
| --- | --- |
| Admin | Manage users, students, teachers, groups, schedules, settings, and spreadsheet data. |
| Teacher | Review assigned groups, manage schedules, edit lessons, and work with grade data. |
| Student | View lessons, schedules, grades, and personal workspace settings. |

## Engineering Standards

- Keep backend contracts explicit through FastAPI route definitions, Pydantic schemas, and generated OpenAPI docs.
- Keep frontend request and form boundaries typed with TypeScript, TanStack Query, and Zod where appropriate.
- Protect sensitive operations with role checks, token validation, CORS configuration, session middleware, and rate limits.
- Prefer focused tests around authentication, route contracts, and high-risk academic workflows.
- Store secrets outside the repository in local `.env` files or deployment-managed secret stores.

## License

Unified is released under the MIT License.
