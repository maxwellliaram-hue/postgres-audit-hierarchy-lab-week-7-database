
# PostgreSQL Audit, Hierarchy, and Security Lab

## Project overview

This project demonstrates production-ready PostgreSQL engineering practices for audit logging, hierarchical category modeling, versioned migrations, and least-privilege security.

## Objectives

- Implement an audit log using triggers and JSONB payloads.
- Build hierarchical category data with self-referencing tables.
- Manage schema changes with Flyway migrations.
- Enforce least-privilege access using database roles.

## Repository structure

- `migrations/` - Flyway migration scripts for schema creation and setup.
- `audit/` - Audit trigger implementation, tests, and results.
- `hierarchy/` - Category table definition, recursive query, and hierarchy documentation.
- `security/` - Role definitions, user creation, and security notes.
- `docs/` - Design and migration reports plus reflection.

## Migration workflow

1. Place migration scripts in `migrations/`.
2. Run `flyway -url=jdbc:postgresql://localhost/bootcamp -user=postgres migrate`.
3. Check migration status with `flyway info`.

## Audit logging workflow

1. Create `audit_log` table and `audit()` trigger function.
2. Attach `trg_audit` to core tables.
3. Use `audit/audit_test.sql` to confirm updates and deletes are recorded.

## Security implementation summary

- `security/roles_and_permissions.sql` creates `app_read` and `app_write` roles.
- `security/user_creation.sql` creates an `api` user assigned to `app_write`.
- `security/security_notes.md` explains least-privilege principles and role differences.
