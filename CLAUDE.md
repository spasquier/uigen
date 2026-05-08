# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Setup and Database
- `npm run setup`: Install dependencies, generate Prisma client, and run database migrations.
- `npm run db:reset`: Reset the database (forceful).

### Development and Production
- `npm run dev`: Start the development server with Turbopack.
- `npm run build`: Build the application for production.
- `npm run start`: Start the production server.

### Testing and Linting
- `npm run test`: Run unit tests using Vitest.
- `npm run lint`: Run ESLint to check for code quality and errors.

## Project Architecture

### Tech Stack
- **Framework:** Next.js 15 (App Router)
- **UI Library:** React 19, Tailwind CSS v4, Radix UI, Lucide React
- **Language:** TypeScript
- **Database:** SQLite via Prisma ORM
- **AI Integration:** Anthintropic Claude via Vercel AI SDK

### Core Structure
- `src/app/`: Next.js App Router pages, layouts, and API routes.
- `src/components/`: React components (UI, feature-specific, etc.).
- `src/actions/`: Next.js Server Actions for server-side logic.
- `src/hooks/`: Custom React hooks.
- `src/lib/`: Shared utility functions, database clients, and core logic.
- `src/generated/`: Area for generated or transient content.
- `prisma/`: Database schema and migration files.

### Key Concepts
- **AI Component Generation:** The core functionality is generating React components via Claude. These components are managed via a virtual file system and are not written to the disk.
- **Server Actions:** Business logic and database interactions are primarily handled via Server Actions in `src/actions/`.
- **Database:** Uses SQLite. Ensure `npm run setup` is run after significant schema changes.
- **Environment Variables:** Requires `ANTHROPIC_API_KEY` for full functionality. If missing, the app falls back to a mock provider.

### Development Best Practices
- Use comments sparingly. Only comment complex code.

### Database
- The database schema is defined in the @prisma/schema.prisma file. Reference it anytime you need to understand the structure of data
stored in the database.

🤖 Generated with [Claude Code](https://claude.com/claude-code)
