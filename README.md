# Socially

Social media platform with posts, comments, likes and follows, built with Next.js, Prisma and Clerk.

🔗 Live: https://socially-rho-seven.vercel.app/

## Stack

- Next.js
- TypeScript
- PostgreSQL + Prisma (with Accelerate)
- Clerk (authentication)
- UploadThing (image uploads)
- Radix UI
- Tailwind CSS
- date-fns

## Features

- User authentication via Clerk
- Create posts with text and image
- Comment on posts
- Like posts
- Follow/unfollow other users
- Notifications for likes, comments and follows
- User profile with bio, location and website

## Data Model

- **User** — account synced with Clerk, has posts, comments, likes, followers and following
- **Post** — belongs to a user, has comments and likes
- **Comment** — belongs to a post and a user
- **Like** — join table between User and Post, prevents duplicate likes
- **Follows** — join table between two users (follower/following), composite primary key prevents duplicate follows
- **Notification** — triggered by a user action (like, comment, follow), targets another user, optionally linked to a post or comment

## Getting Started

```bash
npm install
npx prisma generate
npx prisma migrate dev
npm run dev
```

Set the following environment variables

```
DATABASE_URL=
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
UPLOADTHING_TOKEN=
```
