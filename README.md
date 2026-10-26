# greg2

Booking site built with Next.js 15 (App Router), Tailwind CSS and MongoDB.
Includes an admin dashboard, Stripe payments, Telegram notifications and
Cloudflare Turnstile protection on the booking form.

## Development

```bash
npm install
cp .env.example .env.local   # fill in the values
npm run dev
```

## Deployment

Deployed on Vercel; every push to `main` triggers a production deploy.
Required environment variables are listed in `.env.example`.

`vercel.json` schedules a daily cron (`/api/cron/expire-bookings`) that expires
unpaid bookings. It requires `CRON_SECRET` to be set, otherwise it returns 500.
