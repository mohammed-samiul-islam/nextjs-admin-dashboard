# Next.js Admin Dashboard

Admin dashboard with GitHub sign-in, a searchable users table from PostgreSQL, and an analytics page with charts.

## Features

- GitHub OAuth sign in/out with NextAuth and the Prisma adapter
- Users page: table of users from the database, searchable by name/email (`?q=`)
- Analytics page with Tremor charts and bar lists (sample/static data)
- Responsive navbar with avatar fallback (Avvvatars)

## Tech Stack

Next.js 14 · TypeScript · React · Tailwind CSS · Tremor · Headless UI · NextAuth · Prisma · PostgreSQL · lucide-react

## Project Structure

```
app/
  page.tsx                    # users table + search
  analytics/page.tsx          # charts
components/                   # Navbar, Nav, Search, UsersTable, Analytics, Chart
lib/prisma.ts
pages/api/auth/[...nextauth].ts
prisma/schema.prisma          # Account, Session, User, VerificationToken
```

## Getting Started

```bash
npm install
npm run prisma:generate
npx prisma db push
npm run dev
```

Other scripts: `npm run build`, `npm run start`, `npm run lint`, `npm run vercel-build` (`prisma generate && next build`).

### Environment Variables

| Name | Purpose |
|------|---------|
| `DATABASE_URL` | PostgreSQL connection string |
| `GITHUB_CLIENT_ID` | GitHub OAuth app client ID |
| `GITHUB_CLIENT_SECRET` | GitHub OAuth app client secret |
| `NEXTAUTH_SECRET` | NextAuth secret |

## Credits

Inspired by [vercel/nextjs-postgres-nextauth-tailwindcss-template](https://github.com/vercel/nextjs-postgres-nextauth-tailwindcss-template).
