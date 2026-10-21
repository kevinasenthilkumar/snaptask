Snap Task
AI-powered screenshot organiser, reminder and cleanup app for Android.

Overview
Screenshots pile up and get forgotten, filling your storage. Snap Task sorts them automatically, reminds you before anything is deleted, and clears out what you no longer need. Everything runs on your device, and nothing is uploaded.

Features
Gallery access to detect screenshots
Automatic categories: tickets, event details, bank details, duplicates
Dated screenshots: reminders 2 days and 1 day before deletion; deleted 1 day after the event date
Undated screenshots: reminder on day 6; deleted after 7 days
"Unsure" category for anything the app can't confidently classify, with a notification asking you to review
Keep option to save a screenshot from deletion
Deletes the gallery copy together with the app's record
Fully on-device: no cloud upload
Architecture
+-------------------+ | UI Layer | Categories, review screen, notifications +---------+---------+ | +---------v---------+ | Application Logic | Categorisation and expiry rules +----+---------+----+ | | +----v---+ +--v-----------+ | On- | | Monitoring & | | device | | Scheduler | Daily expiry checks, reminders, | AI/OCR | | | deletions +----+---+ +--+-----------+ | | +----v---------v----+ | Local Storage | Encrypted database (metadata only) +---------+---------+ | +---------v---------+ | Gallery Access | Read screenshots, delete gallery copies +-------------------+

Data flow
A new screenshot is detected in the gallery.
OCR and classification run on the device.
The app assigns a category and expiry date, or marks it "unsure".
The scheduler sends reminders before expiry.
The user keeps the screenshot, or it is deleted from the app and gallery.
Privacy and security
All processing happens on the device
Encrypted local database
Only the permissions needed (gallery, notifications) are requested
Tech stack
Platform: Android
Framework: to be decided (Flutter or native Kotlin)
Design: Figma
Status
In development.
