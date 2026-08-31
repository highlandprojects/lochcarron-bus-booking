# Service 704 — Lochcarron Garage bus booking

Three pages, all static, all reading the live database directly.

| Page | Who it is for |
|---|---|
| `home.html` | **The one to bookmark.** Links to all four, says which is which. Not linked from the customer page, and marked noindex. |
| `index.html` | The public booking page. |
| `route.html` | The route and every stop, both directions. Linked from the booking page. |
| `staff.html` | **The office.** Taking bookings over the telephone, the day, the call list. Sign-in required — it is deliberately not linked from the public page. |
| `driver.html` | **The driver.** The run in road order, tap people on, walk-ons, end of run. Works with no signal: taps are kept in the phone and send themselves. Sign-in required, and likewise unlinked. |

The pages are built and tested in the main project repository
(`web/book/`, tested by `web/test/run.sh` against a real PostgreSQL with
the real migrations and the real row-level security). What is here is a
copy for hosting; edit them there, not here.

## Addresses

- Now: GitHub Pages, `/index.html`, `/route.html`, `/staff.html`.
- Intended: `lochcarrongarage.com/bus` via Vercel. `vercel.json` maps
  `/bus/` to the booking page and `/bus/<file>` to the rest, so the
  relative links between the three pages keep working.

## What is safe to have in these files

The Supabase URL and the **publishable** key. That key is meant to be
public: everything it can reach is the eight allow-listed functions, and
row-level security decides the rest. There is no service key here, no
password, and nothing that identifies a customer.
