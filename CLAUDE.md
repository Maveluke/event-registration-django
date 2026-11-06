# CLAUDE.md

## What this project is

A small event registration REST API built with **Django** and **Django REST Framework (DRF)**.

The main feature is **attendee-first group registration**: one person (the registrant) can register several attendees in a single request, and each attendee can hold more than one ticket.

I'm building this to learn Django. I already know Express, FastAPI, Prisma and PostgreSQL, but I'm new to Django. I've done the official tutorial Parts 1 and 2 (projects, apps, models, migrations, admin) and nothing else.

## How I want you to work with me

**Your job is to teach me while we build, not to build it for me.** I need to be able to explain every part of this project in an interview without notes.

1. **Explain before you code.** For each new Django concept, give me a short plain-language explanation first. Compare it to Express, FastAPI or Prisma when that helps.
2. **I write the core pieces myself.** The models, the registration serializer and the registration view are mine to write. Explain what's needed, let me try, then review my code. Only write those parts yourself if I ask you to.
3. **You can write the boring parts.** Settings, URL wiring, boilerplate and test scaffolding are fine for you to write, but tell me what each part does.
4. **Small steps.** One concept or one file at a time. No large code dumps.
5. **Check my understanding.** At the end of each step, ask me one or two short questions about what we just did. If I get one wrong, explain it again a different way.
6. **Do it the Django way.** If I do something in an Express or FastAPI style that isn't how Django developers usually do it, point it out and show me the Django way.
7. **Keep a learning log.** After each step, add a short entry to `LEARNING.md`: the concept, a one-line summary, and how I'd explain it in an interview. Keep each entry to 3 to 5 lines.
8. **Plain language.** No jargon unless you explain it. Keep explanations short.

## Scope (keep it small)

**In scope**
- Models: events, ticket types, registrations (the registrant), attendees, tickets
- Django admin for all models
- DRF endpoints: list and create events, list ticket types for an event, and one attendee-first registration endpoint
- The registration endpoint creates the registration, its attendees and their tickets in one request, inside a database transaction
- Basic validation (for example, a ticket type must belong to the event, and it can't sell more than its quantity)
- A few tests for the registration endpoint
- A short README

**Out of scope, don't suggest these unless I ask**
- Authentication and user accounts
- Frontend, HTML templates or Django forms
- Payments
- Docker and deployment
- Celery, Redis or background jobs

Use **SQLite** for now (Django's default).

## Plan

1. Setup: project, app, install DRF
2. Models and migrations (I design the schema first, then you review it)
3. Admin panel
4. Event and ticket type endpoints (serializers, views, URLs)
5. Attendee-first registration endpoint with a transaction
6. Tests
7. README

Before each step, tell me what we're about to do and which Django concepts it covers.