# Lochcarron Garage — Service 704 booking page

The public booking page for the Applecross–Inverness bus (service 704).

- `index.html` — the whole page, one file. Talks to the Supabase database
  through eight audited public functions; contains only the publishable key.
- `vercel.json` — serves the page at `/bus`; the bare domain forwards to the
  main Lochcarron Garage website.

Deployed on Vercel. The public address will be lochcarrongarage.com/bus once
the tandem trial (paper + system side by side) is complete.
