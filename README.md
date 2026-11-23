# Fleet & Operations Tracker

**A mobile-first web app that replaced paper logs, spreadsheets and memory for a 9-person firewood production and delivery business in Alberta.**

I designed it, specified it and brought it to production myself, using AI-assisted development (Claude Code). I made the product, workflow and security decisions; the AI wrote the code under my direction. The app has been in daily use by the whole team since June 2026.

> The source code is private because this is a live system holding a real business's operational data. This repository is a public overview. I'm happy to walk through the app in a demo during an interview.

---

## The problem

The business runs about 12 vehicles and 10 pieces of heavy equipment, and the team works from their own phones. Before this app:

- Registration, insurance and CVIP inspection dates were tracked by memory. A missed renewal means a truck can't legally run.
- Oil changes and greasing were due by engine hours or kilometres, and there was no shared record of what had been done.
- Parts, supplies and firewood stock were counted by hand, with no warning when something ran low.
- Delivery scheduling, time-off requests and day-to-day communication were spread across texts and phone calls.

## What it does

| Area | What the team gets |
|---|---|
| **Assets** | One page per vehicle or machine with its photo, details, full maintenance history and current hours/odometer |
| **Compliance alerts** | Registration, insurance and CVIP expiry dates, with automatic email reminders 14 days, 7 days and 24 hours before each one expires |
| **Maintenance log** | Staff log work from their phones: date, readings, notes, cost and receipt photos |
| **Parts & supplies** | Per-asset parts list (part number, supplier, quantity on hand), a categorized supply room with low-stock warnings, and a request board for reorders |
| **Firewood inventory** | Stock levels by product that are deducted automatically when a delivery is completed |
| **Delivery calendar** | Monthly schedule with an approval step (managers request, the owner approves or reschedules), email reminders the day before and the day of, and drivers confirm the quantity delivered |
| **Time off & scheduling** | Staff time-off requests, plus blocked days such as closures or inspections |
| **Team message board** | A live shared feed on the home screen |
| **Team management** | The owner invites, removes and changes the role of staff without technical help |

## Security and data protection

This app holds business records and staff information, so security was a design requirement from day one:

- **Invite-only accounts.** Nobody can sign up on their own; the owner adds each person.
- **Three permission levels** (staff, management, admin) are enforced in the database itself, not just hidden in the app. A user can't get around them by tampering with their phone.
- **Secure sign-in.** A one-time email link is used for first-time setup; after that, users sign in with a password that has to meet strength rules. Sessions log out automatically after 30 minutes of inactivity.
- **Audit trail.** Every change is recorded with who made it and when, with automatic retention limits.
- **Recoverable deletes.** Most deletions can be undone, and permanent deletion is admin-only.
- **Private documents.** Uploaded files and photos sit in private storage and are never publicly linkable.
- **Canadian data residency.** The database is hosted in Canada.

## How it was built

- **App:** React Native with Expo, so one codebase covers web, iPhone and Android. It's currently deployed as an installable web app (it can be added to a phone's home screen like a native app).
- **Backend:** Supabase (PostgreSQL database, authentication, file storage, scheduled jobs, serverless functions).
- **Email:** a transactional email service for alerts and invites.
- **Hosting:** static web hosting (Netlify).
- **Running cost:** close to $0/month on free tiers.

**My role:** I gathered requirements from the people who'd use it, decided what to build and in what order, set the permission and security rules, tested every feature against real workflows, and handled rollout and training for the team. I built the app by directing an AI coding assistant, and each feature was tested and confirmed working before release.

**Timeline:** discovery began in May 2026; the core app was live within weeks, and features were added in response to team feedback through the summer.

---

**Built by Dan Thompson**
