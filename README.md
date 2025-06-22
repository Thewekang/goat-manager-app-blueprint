# goat-manager-app-blueprint

🐐 Goat Manager App — Continuity Brief (For New Chat)
Project Purpose:
Modern, mobile-friendly, PWA-ready web app for goat farm management: health, breeding, vaccination, removal, dashboard analytics, with fine-grained user roles. Stack: Flask, SQLAlchemy, Bootstrap, Chart.js, FullCalendar, Jinja templates.

1. What Has Been Implemented (MVP & Enhancements)
Data Models & DB:

Goat, GoatType, Sickness (+ SicknessPhoto, multi-upload), BreedingEvent, VaccineType, VaccinationEvent, WeightLog, User, FarmConfig, Removal, TargetWeight, Feedback (Observation/Discussion).

User System:

Roles: superadmin, admin, worker

Permissions: granular (sickness, removal, config, etc.), session-based

Password management:

No "forgot password" for security,

Users request reset; admin/superadmin resets

System-generated temp password (must change at next login)

All users can change their own password

CRUD:

Add/edit/remove goats, breeding, weights, sickness, removals

Batch vaccination, batch entry (weight, vaccine, sickness, pregnancy)

All forms modal/mobile-friendly, multi-photo uploads (camera/file), photo preview and deletion

Health & Tags:

Goat tags auto-computed (pregnant, underweight, sick, ready to mate, etc.), badges everywhere

Observation/Discussion (was Worker Feedback):

Add via modal (multi-photo, preview, delete), only submitter or admin/superadmin can delete

Editable for 1 hour by submitter

All labels updated to "Observation / Discussion"

Dashboard:

Totals, ready does, underweight, sick, overdue vax, recent breeding, charts, color-coded alerts, welcoming banner for logged-in user

Responsive, mobile-friendly, PWA offline support

Vaccination:

Flexible schedule logic, auto/reschedule, batch entry, due/soon/overdue color alerts

Breeding:

Add/edit/delete/history, quick entry, batch, dashboard stats

Calendar:

FullCalendar with matings, vaccinations, custom events, recurrence

Quick Entry:

Tabbed menu for: Weight, Sickness, Vaccination, Pregnancy, Add Breeding, Add Goat

Pagination:

All long tables (weight, sickness, vax, breeding) now paginated (10 per page, Bootstrap navigation, fast for large data)

Service Worker & Manifest:

Full PWA: installable, offline static cache

Custom CSS/UX:

Floating alerts (no scroll jump, reusable), print-friendly

All forms, modals, nav responsive/mobile

Consistent iconography (Bootstrap Icons)

2. Pending Features / Next Steps
(Copy these as TODOs/bookmarks/future sprints):

Export/print/download: health, vaccination, breeding, removal logs

Clickable tags: tag badge links jump to filtered pages/actions

Calendar coloring/badges: improve overdue/upcoming

Batch Operations: further batch edit/delete for weights, health, removal

Profile image for goat: support upload, cropping

Soft/Hard delete: with archive/restore logic

More custom dashboards: timeline, per-location, heatmaps

Advanced PWA: queued actions, better offline sync

Accessibility audit

Notification system: admin/worker dashboard notices

Integration with WhatsApp/SMS/email for reminders

Removals: Death/removal with certificate upload, detailed reason tracking

3. Best Practices Used
Server-side pagination (scalable for thousands of rows)

Route-level permission checks (role+ownership for all sensitive actions)

All file uploads/deletes checked for permission

Session-based login, password reset workflow is secure (no forgotten password exposure)

Modular/expandable structure ready for refactoring to models.py in future

