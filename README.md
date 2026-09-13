# Bibliotheca

### A Full-Stack Digital Library Management System

Bibliotheca is a web-based e-library management platform designed to modernize traditional library workflows for academic institutions and knowledge-sharing communities.

The system provides separate experiences for **students/users and librarians**, allowing users to discover, request, read, and return e-books while giving the librarian centralized control over books, sections, user access, and activity.

The platform combines a **Vue.js frontend**, **Flask backend**, **MySQL database**, and **Redis + Celery** for asynchronous background processing and scheduled tasks.

---

## Overview

Traditional library workflows often involve manual processes for:

- Book availability tracking
- Borrowing and return records
- User management
- Book categorization
- Due-date monitoring
- Activity reporting

Bibliotheca digitizes these workflows into a centralized platform.

The system supports:

- User authentication
- Role-based access control
- E-book discovery
- Book requests and returns
- Automatic access expiry
- Book and section management
- User activity tracking
- Feedback and ratings
- Asynchronous background jobs
- Scheduled notifications
- Monthly activity reports

The application is designed to be scalable and extensible, with additional capabilities such as recommendation systems, mobile access, OCR, and institutional authentication planned for future iterations. :contentReference[oaicite:1]{index=1}

---

# System Architecture

```text
                         ┌─────────────────────┐
                         │       Users         │
                         │ Students / Faculty  │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    Vue.js Frontend  │
                         │ HTML5 / CSS3 /      │
                         │ Bootstrap            │
                         └──────────┬──────────┘
                                    │
                              HTTP / API
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    Flask Backend    │
                         │ Routing / APIs /    │
                         │ Business Logic      │
                         └───────┬─────┬───────┘
                                 │     │
                    ┌────────────┘     └─────────────┐
                    ▼                                ▼
          ┌─────────────────┐              ┌─────────────────┐
          │     MySQL       │              │ Redis + Celery  │
          │                 │              │                 │
          │ Users           │              │ Background Jobs │
          │ Books           │              │ Notifications   │
          │ Sections        │              │ Search Indexing │
          │ Activity Logs   │              │ Reports         │
          └─────────────────┘              └─────────────────┘
