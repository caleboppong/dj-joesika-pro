# DJ Joesika Pro Website

Professional React + Vite DJ website with WhatsApp booking, TikTok video section, responsive design and optional Supabase-backed booking/live request storage.

## Run immediately
1. Install Node.js (Vite currently requires a supported modern Node version).
2. Open this folder in VS Code/terminal.
3. Run: `npm install`
4. Run: `npm run dev`
5. Open the localhost address Vite shows (normally http://localhost:5173).

The site works without Supabase: bookings and live requests open WhatsApp to +44 7459 742667.

## Enable database + live requests
1. Create a Supabase project.
2. Open SQL Editor and run `supabase/setup.sql`.
3. Copy `.env.example` to `.env.local`.
4. Add your Project URL and Publishable Key.
5. Restart `npm run dev`.

New live requests are stored as unapproved. In Supabase Table Editor, change `approved` to true for requests you want displayed publicly on the live request wall.

## Important
The two TikTok player URLs are included in `src/App.jsx`. If TikTok changes the video IDs/embedding behaviour, replace the `TIKTOKS` entries with the current player/embed URLs.

Before public launch, review your Supabase RLS policies and add admin authentication for managing requests/bookings.

## DJ Control Room

1. Run the latest `supabase/setup.sql` in Supabase SQL Editor.
2. In Supabase Authentication > Users, create the DJ's email/password user.
3. Open `/dj` on the website and sign in with that account.
4. Use GO LIVE / END EVENT to open or close public song requests.
5. New requests appear privately in the Control Room. Approve publishes to the public wall; Playing highlights it; Done removes it from the wall; Decline keeps it private.
6. Auto-approve can be enabled for trusted/smaller events.

Supabase remains behind the scenes. The DJ does not need the Supabase dashboard while performing.
