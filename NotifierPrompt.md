Build a complete Flutter mobile app called “Universal Reminder Tracker” that serves as a personal reminder and tracker for all payments, plans, bills, and health events. The app should run offline, be cross-platform (Android & iOS), and be packaged as a single APK. Use Hive DB for local storage and optional free open-source cloud backup. Include notifications, charts, and all features in one app. Do not use Firebase.

1️⃣ Core Features:

Reminder Tracking

Users can add reminders for any recurring or one-time events, including:
Mobile recharge / bills
Electricity / Gas / Water
Insurance / Policies
Tax payments / Investments
Health / Medicines / Tests
Custom reminders
Fields for each reminder:
Title / Name
Category (dropdown)
Amount (optional)
Due Date
Frequency: One-time / Daily / Weekly / Monthly / Yearly / Custom
Notes (optional)
Notification days before due date
2️⃣ UI / UX:
Single main dashboard showing a scrollable list of reminders
Color-coded status:
Green → upcoming
Yellow → due soon (e.g., within 2–3 days)
Red → overdue
Add/Edit Reminder via modal or bottom sheet
Include charts for visualization:
Pie chart: reminders by category
Bar/line chart: total amounts due per month
Option to filter/search reminders by category, name, or due date
3️⃣ Data Storage:
Use Hive DB for local offline storage
Support CRUD operations (create, read, update, delete) for reminders
Optional cloud backup using free open-source solutions (like REST API with JSON backup, GitHub Gist, or Nextcloud)
Offline-first functionality; app works fully without internet
4️⃣ Notifications:
Use flutter_local_notifications for cross-platform notifications
Features:
Notify X days before reminder due date (customizable per reminder)
Recurring reminders (daily, weekly, monthly, yearly, custom intervals)
Notifications work offline and after device restart
Allow user to mark as completed from notification or app
5️⃣ Analytics / Charts:
Dashboard should include:
Pie chart: reminders by category (e.g., Electricity, Insurance, Tax, Health)
Bar chart: total amount due per month
Charts should update automatically when adding or completing reminders
Use fl_chart Flutter library
6️⃣ Architecture:
Models:
Reminder: id, title, category, amount, dueDate, frequency, notes, notificationDaysBefore, isCompleted
Services:
Hive storage service (CRUD)
Notification service (schedule and recurring)
Chart/analytics service
UI:
Screens: Main Dashboard, Add/Edit Reminder Modal
Widgets: Reminder Card, Charts, Filters
7️⃣ Coding Requirements:
Flutter 3+ compatible, null-safety enabled
Clean folder structure: models/, services/, screens/, widgets/
Use Provider or Riverpod for state management
Fully commented code explaining logic
Include sample dummy reminders to test UI, charts, and notifications
Include chart examples using fl_chart for categories and monthly summaries
8️⃣ Optional / Future Enhancements:
Backup and restore data to free open-source cloud (GitHub Gist, JSON API, Nextcloud, etc.)
Export/import reminders via CSV
Custom themes (light/dark mode)
Custom recurring intervals (e.g., every 45 days)
9️⃣ Deliverables:
Complete Flutter project folder ready to run
APK ready for Android
README explaining features, folder structure, and setup
Example screenshots of main dashboard, chart visualizations, and notifications

Instruction to AI agent:

“Generate the full Flutter app code based on the above specification. Include Hive DB for offline storage, local notifications for all reminders, charts using fl_chart, Add/Edit UI, dashboard with color-coded reminders, and optional free cloud backup mechanism. Include dummy data for testing. Provide comments and clean folder structure. The code should produce a working APK.”
