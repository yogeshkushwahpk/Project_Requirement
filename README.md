# 🌐 BlogSphere — MERN Stack Student Capstone Project

[![Stack](https://img.shields.io/badge/Stack-MERN-10b981?style=for-the-badge&logo=mongodb)](https://github.com/)
[![React](https://img.shields.io/badge/Frontend-React%20%7C%20Vite-61dafb?style=for-the-badge&logo=react)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Backend-Node.js%20%7C%20Express-68a063?style=for-the-badge&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/Database-MongoDB%20Atlas-47a248?style=for-the-badge&logo=mongodb)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/Assignment-Capstone%20Project-f59e0b?style=for-the-badge)](https://github.com/)

> **Academic Capstone Project & Industry-Oriented Engineering Assignment**  
> **Course:** Full Stack Web Development (MERN Track)  
> **Target Audience:** Junior Developers & Final Year Students  
> **Project Mode:** Solo Capstone Project  
> **Difficulty Level:** Beginner to Intermediate (Industry Standard Architecture)

---

## 📑 Table of Contents

1. [Executive Summary & Project Overview](#1-executive-summary--project-overview)
2. [Pedagogical Learning Objectives](#2-pedagogical-learning-objectives)
3. [Technology Stack & Architectural Principles](#3-technology-stack--architectural-principles)
4. [User Roles & Access Control Matrix](#4-user-roles--access-control-matrix)
5. [Frontend Page Architecture & UX Specifications](#5-frontend-page-architecture--ux-specifications)
   - [5.1 Public Visitor Pages](#51-public-visitor-pages-45-core-pages)
   - [5.2 Authenticated Author Features](#52-authenticated-author-pages--features)
   - [5.3 Admin CMS & Content Moderation Dashboard](#53-admin-cms--content-moderation-dashboard)
6. [Database Design & Mongoose Schemas](#6-database-design--mongoose-schemas)
   - [6.1 Entity Relationship Diagram (ERD)](#61-entity-relationship-diagram-erd)
   - [6.2 Detailed Model Specifications](#62-detailed-model-specifications)
7. [Comprehensive RESTful API Specification (60+ Endpoints Matrix)](#7-comprehensive-restful-api-specification-60-endpoints-matrix)
8. [Step-by-Step 10-Milestone Implementation Roadmap](#8-step-by-step-10-milestone-implementation-roadmap)
9. [Security, Performance & Validation Standards](#9-security-performance--validation-standards)
10. [Repository Directory & File Structure](#10-repository-directory--file-structure)
11. [Local Development & Environment Setup Guide](#11-local-development--environment-setup-guide)
12. [Student Evaluation Rubric (100-Point Scale)](#12-student-evaluation-rubric-100-point-scale)
13. [Final Submission, Demo & Presentation Checklist](#13-final-submission-demo--presentation-checklist)

---

## 1. Executive Summary & Project Overview

### 1.1 Problem Statement
Modern content publishing platforms (such as Medium, Dev.to, and Hashnode) operate as distributed, multi-tier web systems. They require seamless handling of public readership, author editorial workflows, social interactions (likes, comments, bookmarks), asset management, and administrative moderation.

Most beginner tutorials teach disconnected concepts: a standalone React counter, a basic Express "Hello World", or isolated MongoDB CRUD operations. Students rarely experience how these components synthesize into a cohesive, secure, multi-role web platform.

### 1.2 The Capstone Goal
**BlogSphere** is an industry-grade, full-stack blogging platform and Content Management System (CMS) designed specifically as a student capstone assignment. 

As a **solo developer**, each student will engineer BlogSphere from scratch using the **MERN Stack** (MongoDB, Express.js, React.js, and Node.js). By building this application, students bridge the gap between academic theory and real-world software engineering practices—delivering clean React components, robust REST APIs with authentication and role-based access control, relational-style data models in MongoDB, server-side pagination/filtering, file handling, and administrative analytics dashboards.

---

## 2. Pedagogical Learning Objectives

Upon successful completion of the BlogSphere solo capstone, students will be able to:

- **Full-Stack System Architecture:** Understand request-response cycles, RESTful design patterns, stateless client-server communication, and separation of concerns.
- **Modern React & UI Engineering:** Structure reusable React functional components, leverage React Router v6 for dynamic client-side routing, handle form state, and manage global authentication state via the Context API.
- **Backend API Engineering:** Build clean, modular Express routers, controllers, and services with centralized error handling and standard JSON responses.
- **Database Modeling with MongoDB & Mongoose:** Implement relational schema associations (`ref`), compound indexes, virtual populate, pre-save middleware hooks, and aggregation pipelines.
- **Authentication & Authorization:** Secure web applications with JSON Web Tokens (JWT), bcrypt password hashing, and role-based access control (RBAC) protecting endpoints at both the API and client routing levels.
- **Content Management & Moderation:** Build dual-facing user experiences—a clean public reading portal for guests alongside a secure administrative CMS dashboard for platform oversight.
- **Security & Quality Assurance:** Implement input sanitization (preventing XSS and NoSQL injection), CORS whitelisting, file validation with Multer, API rate limiting, and environment variable isolation.
- **DevOps & Professional Tooling:** Maintain professional Git workflows, author API documentation, test with Postman, and deploy full-stack applications to cloud platforms (Vercel, Render, and MongoDB Atlas).

---

## 3. Technology Stack & Architectural Principles

```
┌────────────────────────────────────────────────────────────────────────┐
│                          CLIENT-SIDE (React + Vite)                    │
│   React Router v6  •  Context API (Auth)  •  Vanilla CSS Design System │
│   Axios / Fetch Client  •  Markdown / Rich Text Editor Integration     │
└────────────────────────────────────▲───────────────────────────────────┘
                                     │ HTTP / HTTPS (JSON)
                                     │ JWT Bearer Authorization
┌────────────────────────────────────▼───────────────────────────────────┐
│                          SERVER-SIDE (Node.js + Express)               │
│   Express Router  •  JWT Auth Middleware  •  RBAC (User/Admin)         │
│   Multer (File Uploads)  •  Rate Limiter  •  Central Error Handler     │
└────────────────────────────────────▲───────────────────────────────────┘
                                     │ Mongoose ODM Driver
┌────────────────────────────────────▼───────────────────────────────────┐
│                          DATABASE (MongoDB Atlas)                      │
│   Users  •  Blogs  •  Categories  •  Comments  •  Likes  •  Bookmarks  │
└────────────────────────────────────────────────────────────────────────┘
```

### 3.1 Technology Breakdown

| Layer | Technology | Selection Rationale |
| :--- | :--- | :--- |
| **Frontend Runtime** | **React.js 18+ (Vite)** | Lightning-fast HMR build tool, minimal boilerplate, modern JSX standard. |
| **Client Routing** | **React Router v6** | Declarative client-side routing with nested layouts and protected route wrappers. |
| **Client State** | **React Context API** | Native state management for authentication and notifications without Redux complexity. |
| **Styling** | **Vanilla CSS3** | Custom design system using CSS variables, flexbox, grid, and fluid typography. (No utility framework lock-in). |
| **Backend Runtime** | **Node.js (v18+)** | Asynchronous, non-blocking event-driven runtime ideal for I/O bound web applications. |
| **Web Framework** | **Express.js** | Minimalist web framework offering granular control over middleware pipelines and routing. |
| **Database** | **MongoDB (Atlas / Community)** | Document-oriented NoSQL database optimized for rich, nested editorial content. |
| **ODM Driver** | **Mongoose (v7+)** | Schema enforcement, data validation, middleware hooks, and model-level business logic. |
| **Auth & Security** | **JWT & bcrypt.js** | Stateless token authentication combined with salted password hashing (min 10 rounds). |
| **Asset Storage** | **Multer** | Multipart form-data parser with file-type whitelisting and size limits for image uploads. |

---

## 4. User Roles & Access Control Matrix

The platform enforces three clear tiers of access control:

```
                  ┌──────────────────────┐
                  │      Guest User      │ (Unauthenticated)
                  └──────────┬───────────┘
                             │ Register / Login
                  ┌──────────▼───────────┐
                  │   Registered User    │ (Author / Reader)
                  └──────────┬───────────┘
                             │ Role Escalation (isRole: 'admin')
                  ┌──────────▼───────────┐
                  │    Platform Admin    │ (Superuser / CMS Manager)
                  └──────────────────────┘
```

### 4.1 Feature & Permission Matrix

| Capability / Feature | Guest | Registered User | Platform Admin |
| :--- | :---: | :---: | :---: |
| Browse & search published blogs | ✅ | ✅ | ✅ |
| Filter by category and tags | ✅ | ✅ | ✅ |
| Read blog articles and view count | ✅ | ✅ | ✅ |
| View public author profiles | ✅ | ✅ | ✅ |
| Submit contact inquiries | ✅ | ✅ | ✅ |
| Register and authenticate | ✅ | — | — |
| Create a new blog post | ❌ | ✅ | ✅ |
| Save blogs as drafts | ❌ | ✅ | ✅ |
| Edit & delete **own** blogs | ❌ | ✅ | ✅ |
| Like & unlike blog posts | ❌ | ✅ | ✅ |
| Bookmark blogs to personal reading list | ❌ | ✅ | ✅ |
| Post, edit, and delete **own** comments | ❌ | ✅ | ✅ |
| Edit personal profile & upload avatar | ❌ | ✅ | ✅ |
| Access personal author dashboard | ❌ | ✅ | ✅ |
| **Access Admin CMS Dashboard** | ❌ | ❌ | ✅ |
| **Edit / delete ANY user's blog** | ❌ | ❌ | ✅ |
| **Moderate / delete ANY comment** | ❌ | ❌ | ✅ |
| **Feature / Pin blogs on Homepage** | ❌ | ❌ | ✅ |
| **Manage categories (Create, Edit, Delete)** | ❌ | ❌ | ✅ |
| **Manage users (Suspend, Ban, Promote)** | ❌ | ❌ | ✅ |
| **View system analytics & stats** | ❌ | ❌ | ✅ |
| **View & manage contact inquiries** | ❌ | ❌ | ✅ |

---

## 5. Frontend Page Architecture & UX Specifications

The frontend must feature a **clean, modern editorial aesthetic** with crisp typography, balanced white space, smooth micro-interactions, responsive image layouts, and accessible forms.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        RESPONSIVE NAVBAR                               │
│  [Logo: BlogSphere]   Explore   Categories   About   Contact  [Login/Write]│
├────────────────────────────────────────────────────────────────────────┤
│                                                                        │
│                      CURRENT VIEW (PAGE OUTLET)                        │
│                                                                        │
├────────────────────────────────────────────────────────────────────────┤
│                        RESPONSIVE FOOTER                               │
│  [About]   [Quick Links]   [Category Cloud]   [Newsletter]  [Copyright]│
└────────────────────────────────────────────────────────────────────────┘
```

### 5.1 Public Visitor Pages (4–5 Core Pages)

#### 1. Home Page (`/`)
- **Hero Section:** Engaging headline, platform value proposition, dynamic search bar, and primary "Start Reading" & "Write a Story" CTAs.
- **Featured Articles Carousel / Grid:** Highlights articles flagged as `isFeatured: true` by the Admin.
- **Trending Topics / Category Pills:** Quick-click tags to jump straight into specific technical domains.
- **Recent Publications Feed:** Grid of blog cards displaying title, cover image, category badge, excerpt, author avatar, date, and estimated reading time.
- **Author Spotlight / Community Counter:** Displays total published articles, active writers, and reader community milestones.
- **Newsletter Subscription Card:** Mockup form with client-side email validation.

#### 2. Blog Listing & Explore Page (`/blogs`)
- **Advanced Search Bar:** Live search queries with debouncing.
- **Multi-Filter Sidebar / Bar:** Category dropdown, tag cloud filter, and publication date sort (`Newest`, `Oldest`, `Most Liked`, `Most Viewed`).
- **Active Filter Badges:** Displays active filter chips with a one-click "Clear All Filters" button.
- **Server-Side Paginated Grid:** Displays 6–9 blog cards per page with `Previous`, `Next`, and numbered page controls.
- **Empty State Display:** A polished empty state with an icon and clear CTA when no search results match.

#### 3. Blog Details / Reader Page (`/blogs/:slug`)
- **Article Header:** Full-width cover image, category badge, reading time, publication date, view counter, and author info card.
- **Formatted Article Body:** Clean typography layout with formatted headings, quotes, code blocks, and embedded images.
- **Interactive Action Bar:** Floating or sticky bar with Like button (shows like count + heart animation), Bookmark button, and social share links.
- **Author Bio Card:** Author avatar, bio, follower count, and a "More from this author" section.
- **Interactive Comments Section:**
  - Real-time comment submission box (accessible only when authenticated; prompts guests to log in).
  - List of existing comments with timestamps and author avatars.
  - Inline edit and delete buttons for comments owned by the active user.
- **Related Articles Recommendations:** 3 related blogs from the same category.

#### 4. Author Public Profile Page (`/authors/:id`)
- **Author Identity Header:** Profile avatar, display name, member since date, social links (GitHub, Twitter, LinkedIn), and bio.
- **Author Statistics:** Total blogs written, total likes received, and total article views.
- **Author's Published Articles:** Grid of public blog cards authored by this specific user.

#### 5. About & Contact Page (`/about` & `/contact`)
- **About BlogSphere:** Mission statement, technology stack showcase, and student project attribution.
- **Contact / Feedback Form:** Name, email, subject, message inputs with validation. Directly submits to the `/api/v1/inquiries` API.
- **Frequently Asked Questions (FAQ):** Accordion component addressing publishing guidelines, markdown support, and user accounts.

---

### 5.2 Authenticated Author Pages & Features

#### 6. User Authentication Pages (`/login` & `/register`)
- **Registration Form:** Full name, email, password, and confirm password with live strength validation.
- **Login Form:** Email and password with "Remember Me" toggle and friendly error banners for invalid credentials.
- **Protected Routing:** Automatically redirects authenticated users away from auth pages to `/dashboard`.

#### 7. Author Editorial Dashboard (`/dashboard`)
- **Author Metrics Cards:** Total Articles Written, Total Views, Total Likes, and Total Drafts.
- **Tabbed Management Views:**
  - **Tab 1: Published Articles:** Table/cards showing status, publication date, view count, like count, with `Edit`, `View`, and `Delete` actions.
  - **Tab 2: Drafts & In-Progress:** Blogs saved as drafts with a one-click "Publish Now" button.
- **Quick Create Button:** Prominent floating CTA linking to the article editor.

#### 8. Create & Edit Blog Editor (`/blogs/create` & `/blogs/edit/:id`)
- **Title Input:** Auto-generates URL-friendly slug.
- **Excerpt / Summary Input:** Short 150-character synopsis for card previews.
- **Category & Tag Selector:** Category dropdown populated from database + comma-separated tag input.
- **Cover Image Uploader:** File picker supporting direct upload via Multer or external image URL input with live preview.
- **Content Editor:** Multi-line markdown/rich text input with live preview toggle.
- **Publication Actions:** "Save as Draft" vs "Publish Article" action buttons.

#### 9. Personal Reading List / Bookmarks (`/bookmarks`)
- Displays all articles saved by the user for later reading.
- One-click "Remove from Bookmarks" action with smooth UI removal.

#### 10. User Profile & Settings Page (`/profile`)
- Update display name, bio, and social links.
- Profile avatar upload with live image preview.
- Password change form (requires current password verification).

---

### 5.3 Admin CMS & Content Moderation Dashboard

> **Mandatory Capstone Requirement:** The application must provide a dedicated `/admin` dashboard restricted exclusively to users holding the `admin` role.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        ADMIN CMS DASHBOARD                             │
├───────────────┬────────────────────────────────────────────────────────┤
│  NAVIGATION   │                     MAIN STAGE                         │
│               │                                                        │
│  📊 Overview  │  [Stats: 120 Users | 340 Blogs | 1.2k Likes | 45 Inq] │
│  📝 All Blogs │                                                        │
│  👥 Users     │  ┌──────────────────────────────────────────────────┐  │
│  🏷️ Taxonomy  │  │  SYSTEM METRICS & CONTENT MANAGEMENT TABLES     │  │
│  💬 Comments  │  │  Filter • Search • Bulk Status • Moderate       │  │
│  📬 Inquiries │  └──────────────────────────────────────────────────┘  │
└───────────────┴────────────────────────────────────────────────────────┘
```

The Admin CMS contains five functional modules:

1. **System Overview & Metrics (`/admin/dashboard`):**
   - KPI metric cards: Total Registered Users, Total Published Blogs, Total Drafts, Total Comments, and Active Inquiries.
   - Recent activity feed showing newly registered users and latest submissions.
2. **Global Blog Management (`/admin/blogs`):**
   - View every article in the database across all authors.
   - Filter by status (`Published`, `Draft`, `Under Review`).
   - Feature/Unfeature articles on the homepage with a single toggle.
   - Delete inappropriate, plagiarized, or spam content.
3. **User Management (`/admin/users`):**
   - Paginated table of all registered users with role indicators (`user` vs `admin`).
   - Change user roles (promote author to admin).
   - Suspend or deactivate abusive accounts.
4. **Category & Taxonomy Manager (`/admin/categories`):**
   - Create new categories (Name, Description, Slug, Icon).
   - Edit or delete categories with validation preventing deletion of categories containing active blogs.
5. **Inquiries & Feedback Manager (`/admin/inquiries`):**
   - View messages submitted via the public Contact page.
   - Mark messages as `Read` or `Resolved`.

---

## 6. Database Design & Mongoose Schemas

### 6.1 Detailed Model Specifications

#### 1. User Model (`models/User.js`)
- `name`: String, required, trim, minlength 2, maxlength 50.
- `email`: String, required, unique, lowercase, trim, match standard email regex.
- `password`: String, required, minlength 6 (select: false in queries to avoid password leaks).
- `role`: String, enum: `['user', 'admin']`, default: `'user'`.
- `avatar`: String, default avatar URL.
- `bio`: String, maxlength 250, default: `''`.
- `socialLinks`: Object containing `github`, `twitter`, `linkedin` (optional strings).
- `isSuspended`: Boolean, default: `false`.
- `timestamps`: `true` (`createdAt`, `updatedAt`).

#### 2. Category Model (`models/Category.js`)
- `name`: String, required, unique, trim, maxlength 40.
- `slug`: String, required, unique, lowercase.
- `description`: String, maxlength 200.
- `icon`: String (URL or icon identifier).
- `timestamps`: `true`.

#### 3. Blog Model (`models/Blog.js`)
- `title`: String, required, trim, minlength 5, maxlength 150.
- `slug`: String, required, unique, lowercase, index: true.
- `excerpt`: String, required, maxlength 250.
- `content`: String, required.
- `coverImage`: String, default: curated editorial cover URL.
- `author`: ObjectId, ref: `'User'`, required, index: true.
- `category`: ObjectId, ref: `'Category'`, required, index: true.
- `tags`: Array of strings, default: `[]`, index: true.
- `status`: String, enum: `['draft', 'published']`, default: `'draft'`, index: true.
- `isFeatured`: Boolean, default: `false`, index: true.
- `viewsCount`: Number, default: 0.
- `likesCount`: Number, default: 0.
- `timestamps`: `true`.

#### 4. Comment Model (`models/Comment.js`)
- `blog`: ObjectId, ref: `'Blog'`, required, index: true.
- `author`: ObjectId, ref: `'User'`, required.
- `content`: String, required, trim, minlength 1, maxlength 1000.
- `isEdited`: Boolean, default: `false`.
- `timestamps`: `true`.

#### 5. Like Model (`models/Like.js`)
- `blog`: ObjectId, ref: `'Blog'`, required, index: true.
- `user`: ObjectId, ref: `'User'`, required, index: true.
- `createdAt`: Date, default: `Date.now`.
- **Compound Unique Index:** `{ blog: 1, user: 1 }` with `{ unique: true }` (strictly prevents duplicate likes at database level).

#### 6. Bookmark Model (`models/Bookmark.js`)
- `blog`: ObjectId, ref: `'Blog'`, required, index: true.
- `user`: ObjectId, ref: `'User'`, required, index: true.
- `createdAt`: Date, default: `Date.now`.
- **Compound Unique Index:** `{ blog: 1, user: 1 }` with `{ unique: true }` (strictly prevents duplicate bookmarks).

#### 7. ContactMessage Model (`models/ContactMessage.js`)
- `name`: String, required, trim.
- `email`: String, required, trim, lowercase.
- `subject`: String, required, trim.
- `message`: String, required, trim.
- `status`: String, enum: `['new', 'read', 'resolved']`, default: `'new'`.
- `createdAt`: Date, default: `Date.now`.

---

## 7. Comprehensive RESTful API Specification (60+ Endpoints Matrix)

Students must design and implement the following production-grade REST APIs adhering to standard HTTP verbs, status codes, and JSON response envelopes:

```json
{
  "success": true,
  "message": "Resource retrieved successfully",
  "data": { ... },
  "meta": { "total": 42, "page": 1, "limit": 10 }
}
```

### Complete API Directory (62 Structured Endpoints)

| # | Group | Method | Endpoint URL | Auth Level | Purpose / Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Auth | `POST` | `/api/v1/auth/register` | Public | Register a new user account with hashed password |
| **2** | Auth | `POST` | `/api/v1/auth/login` | Public | Authenticate user and return signed JWT token |
| **3** | Auth | `GET` | `/api/v1/auth/me` | Authenticated | Retrieve currently logged-in user profile details |
| **4** | Auth | `POST` | `/api/v1/auth/logout` | Authenticated | Terminate session / clear auth state |
| **5** | Auth | `PUT` | `/api/v1/auth/change-password` | Authenticated | Verify current password and set new password |
| **6** | Auth | `POST` | `/api/v1/auth/forgot-password` | Public | Request password reset token via email |
| **7** | Auth | `POST` | `/api/v1/auth/reset-password` | Public | Consume token to establish new password |
| **8** | Auth | `GET` | `/api/v1/auth/verify-token` | Authenticated | Verify token validity on page reload |
| **9** | Users | `GET` | `/api/v1/users/profile` | Authenticated | Get detailed profile settings of active user |
| **10** | Users | `PATCH` | `/api/v1/users/profile` | Authenticated | Update user name, bio, and social links |
| **11** | Users | `POST` | `/api/v1/users/avatar` | Authenticated | Upload and set profile avatar image |
| **12** | Users | `GET` | `/api/v1/users/authors` | Public | List all featured authors with article counts |
| **13** | Users | `GET` | `/api/v1/users/:id` | Public | Get public author profile card and biography |
| **14** | Users | `GET` | `/api/v1/users/:id/blogs` | Public | Get public list of published blogs by specific author |
| **15** | Blogs | `GET` | `/api/v1/blogs` | Public | List published blogs with search, category & pagination |
| **16** | Blogs | `GET` | `/api/v1/blogs/featured` | Public | Retrieve top articles flagged as featured |
| **17** | Blogs | `GET` | `/api/v1/blogs/trending` | Public | Retrieve top 5 most viewed/liked articles |
| **18** | Blogs | `GET` | `/api/v1/blogs/recent` | Public | Retrieve 6 most recently published blogs |
| **19** | Blogs | `GET` | `/api/v1/blogs/slug/:slug` | Public | Retrieve full blog details by unique slug |
| **20** | Blogs | `GET` | `/api/v1/blogs/:id` | Public | Retrieve full blog details by ID |
| **21** | Blogs | `GET` | `/api/v1/blogs/:id/related` | Public | Retrieve 3 related articles from same category |
| **22** | Blogs | `POST` | `/api/v1/blogs/:id/view` | Public | Atomically increment article view counter |
| **23** | Blog CRUD | `POST` | `/api/v1/blogs` | Authenticated | Create a new blog (either draft or published) |
| **24** | Blog CRUD | `PUT` | `/api/v1/blogs/:id` | Owner / Admin | Update blog content, title, tags, or category |
| **25** | Blog CRUD | `DELETE` | `/api/v1/blogs/:id` | Owner / Admin | Permanently delete blog and linked comments/likes |
| **26** | Blog CRUD | `PATCH` | `/api/v1/blogs/:id/publish` | Owner / Admin | Change draft status to published |
| **27** | Blog CRUD | `PATCH` | `/api/v1/blogs/:id/unpublish` | Owner / Admin | Revert published blog back to draft |
| **28** | Blog CRUD | `GET` | `/api/v1/blogs/my/all` | Authenticated | Get all blogs (drafts + published) by logged-in user |
| **29** | Blog CRUD | `GET` | `/api/v1/blogs/my/drafts` | Authenticated | Get only unpublished drafts by logged-in user |
| **30** | Blog CRUD | `GET` | `/api/v1/blogs/my/stats` | Authenticated | Get personal view count, like count, and total posts |
| **31** | Comments | `GET` | `/api/v1/blogs/:id/comments` | Public | Get all comments for a blog post (newest first) |
| **32** | Comments | `POST` | `/api/v1/blogs/:id/comments` | Authenticated | Post a new comment on a published blog |
| **33** | Comments | `PATCH` | `/api/v1/comments/:id` | Owner | Edit an existing comment authored by user |
| **34** | Comments | `DELETE` | `/api/v1/comments/:id` | Owner / Admin | Delete comment from article |
| **35** | Comments | `GET` | `/api/v1/comments/my` | Authenticated | Get all comments authored by logged-in user |
| **36** | Comments | `POST` | `/api/v1/comments/:id/flag` | Authenticated | Report / flag inappropriate comment for moderation |
| **37** | Likes | `POST` | `/api/v1/blogs/:id/like` | Authenticated | Like a blog (prevents duplicate likes) |
| **38** | Likes | `DELETE` | `/api/v1/blogs/:id/like` | Authenticated | Remove like from a blog |
| **39** | Likes | `GET` | `/api/v1/blogs/:id/like-status` | Authenticated | Check if current user has liked the blog |
| **40** | Likes | `GET` | `/api/v1/blogs/:id/likers` | Public | List users who liked the blog (avatar & name) |
| **41** | Bookmarks | `GET` | `/api/v1/bookmarks` | Authenticated | Get personal bookmarked articles with pagination |
| **42** | Bookmarks | `POST` | `/api/v1/bookmarks/:blogId` | Authenticated | Bookmark article for later reading |
| **43** | Bookmarks | `DELETE` | `/api/v1/bookmarks/:blogId` | Authenticated | Remove article from personal bookmarks |
| **44** | Bookmarks | `GET` | `/api/v1/bookmarks/check/:blogId` | Authenticated | Check if article is currently bookmarked by user |
| **45** | Categories | `GET` | `/api/v1/categories` | Public | List all categories with associated blog counts |
| **46** | Categories | `GET` | `/api/v1/categories/:slug` | Public | Get single category details by slug |
| **47** | Categories | `POST` | `/api/v1/categories` | Admin Only | Create a new blog category |
| **48** | Categories | `PUT` | `/api/v1/categories/:id` | Admin Only | Update category name, slug, or description |
| **49** | Categories | `DELETE` | `/api/v1/categories/:id` | Admin Only | Delete category (blocked if blogs are linked) |
| **50** | Tags | `GET` | `/api/v1/tags/popular` | Public | List top 15 most frequently used tags |
| **51** | Media | `POST` | `/api/v1/uploads/cover` | Authenticated | Upload blog cover image via Multer (max 5MB) |
| **52** | Media | `POST` | `/api/v1/uploads/avatar` | Authenticated | Upload user profile avatar (max 2MB) |
| **53** | Admin CMS | `GET` | `/api/v1/admin/stats` | Admin Only | Get platform analytics (total users, blogs, views) |
| **54** | Admin CMS | `GET` | `/api/v1/admin/users` | Admin Only | List all platform users with roles and status |
| **55** | Admin CMS | `PATCH` | `/api/v1/admin/users/:id/role` | Admin Only | Promote or demote user role (`user` / `admin`) |
| **56** | Admin CMS | `PATCH` | `/api/v1/admin/users/:id/status`| Admin Only | Suspend or reactivate user account |
| **57** | Admin CMS | `GET` | `/api/v1/admin/blogs` | Admin Only | List all platform blogs across all authors & statuses |
| **58** | Admin CMS | `PATCH` | `/api/v1/admin/blogs/:id/feature`| Admin Only | Toggle featured status of any blog post |
| **59** | Admin CMS | `DELETE` | `/api/v1/admin/blogs/:id` | Admin Only | Admin force delete any blog post |
| **60** | Admin CMS | `GET` | `/api/v1/admin/comments/flagged`| Admin Only | View list of flagged comments for moderation |
| **61** | Inquiries | `POST` | `/api/v1/inquiries` | Public | Submit contact message from Contact page |
| **62** | Inquiries | `GET` | `/api/v1/admin/inquiries` | Admin Only | View all submitted inquiries |

---

## 8. Step-by-Step 10-Milestone Implementation Roadmap

Students must structure their work sequentially across **10 structured development milestones**. Do not jump ahead until the current milestone is fully verified.

```
 Milestone 1: Environment Setup, Project Structure & Static UI Layout
      │
 Milestone 2: React Router v6, 4-5 Public Pages & Navigation Flows
      │
 Milestone 3: Express Server, MongoDB Atlas Connection & Error Framework
      │
 Milestone 4: Blog Models, Controllers & Public REST APIs
      │
 Milestone 5: JWT Auth, Password Hashing, Context API & Route Protection
      │
 Milestone 6: Blog Ownership, Author Dashboard, Drafts & Publishing
      │
 Milestone 7: Engagement Engine: Comments, Likes & Bookmarks
      │
 Milestone 8: Search Engine, Categories, Multi-Filtering & Pagination
      │
 Milestone 9: Admin CMS Dashboard, RBAC & Content Moderation
      │
 Milestone 10: Multer File Uploads, Security Hardening, Testing & Deployment
```

---

### Milestone 1: Environment Setup, Directory Structure & Static UI Layout
- **Goal:** Set up clean monorepo architecture, establish UI design tokens (typography, color palettes, spacing), and build the core static shell.
- **Key Tasks:**
  1. Initialize root workspace and establish `/client` and `/server` directories.
  2. Scaffold React client using Vite (`npm create vite@latest client -- --template react`).
  3. Define custom Vanilla CSS design system (`index.css`) with CSS custom properties (variables for colors, fonts, radius, elevations).
  4. Build responsive `Navbar` component with mobile hamburger toggle and brand identity.
  5. Build comprehensive `Footer` with navigation links, category cloud, and newsletter card.
  6. Create `BlogCard` component using mock editorial data to verify responsive card layout.
- **Verification:** Run `npm run dev` in `/client`. Navbar, Footer, and cards must render cleanly across mobile (375px), tablet (768px), and desktop (1280px).

---

### Milestone 2: React Router v6 & Public Page Architecture
- **Goal:** Transform static components into a multi-page single-page application (SPA) with declarative client-side routing.
- **Key Tasks:**
  1. Install `react-router-dom` in client.
  2. Configure `<BrowserRouter>` with root `<Layout>` wrapper containing `<Navbar>`, `<Outlet />`, and `<Footer>`.
  3. Implement 5 core public pages:
     - `HomePage.jsx`: Hero banner, featured cards, category tabs, and recent blogs list.
     - `BlogListingPage.jsx`: Filterable article explore catalog.
     - `BlogDetailPage.jsx`: Full-page article view with author bio and dummy comments.
     - `AuthorProfilePage.jsx`: Public author information and article portfolio.
     - `AboutContactPage.jsx`: Platform narrative and responsive contact form.
  4. Implement `NotFoundPage.jsx` (404) for unknown URL paths.
- **Verification:** Click every link in Navbar and on cards; verify URL paths update without triggering full browser reloads.

---

### Milestone 3: Express Server & MongoDB Connection
- **Goal:** Create the backend Node.js runtime, configure Express middleware, and establish a resilient MongoDB connection.
- **Key Tasks:**
  1. Initialize `package.json` in `/server` and install dependencies: `express`, `mongoose`, `dotenv`, `cors`, `morgan`.
  2. Create modular file structure: `/src/config`, `/src/controllers`, `/src/models`, `/src/routes`, `/src/middleware`.
  3. Configure MongoDB connection in `config/db.js` with connection pooling and error listeners.
  4. Create centralized error handling middleware (`middleware/errorHandler.js`) and 404 route handler.
  5. Implement `GET /api/v1/health` endpoint returning server uptime, timestamp, and database status.
- **Verification:** Start server with `npm run dev`. Confirm `"MongoDB Connected successfully"` appears in terminal and `/api/v1/health` returns status `200 OK`.

---

### Milestone 4: Blog CRUD APIs & Frontend Data Integration
- **Goal:** Build the first end-to-end slice connecting React frontend to MongoDB database through Express REST APIs.
- **Key Tasks:**
  1. Create `models/Category.js` and `models/Blog.js` with validation constraints and slug generation.
  2. Implement seed script (`scripts/seed.js`) to populate 5 categories and 10 realistic sample blogs into MongoDB.
  3. Create `routes/blogRoutes.js` and `controllers/blogController.js`:
     - `GET /api/v1/blogs` (fetch all published blogs)
     - `GET /api/v1/blogs/:id` and `GET /api/v1/blogs/slug/:slug` (fetch single blog)
  4. Build reusable frontend API client (`services/api.js`) using Fetch API or Axios.
  5. Replace static dummy data in `HomePage` and `BlogListingPage` with live data fetched via `useEffect`.
  6. Add `LoadingSpinner` and `ErrorMessage` components for network state feedback.
- **Verification:** Add a new blog directly in MongoDB Compass; refresh the React app and confirm the new blog renders dynamically on the Home page.

---

### Milestone 5: User Registration, JWT Authentication & Protected Routes
- **Goal:** Implement secure user identity, password hashing, stateless token issuance, and protected client views.
- **Key Tasks:**
  1. Install `bcryptjs` and `jsonwebtoken` in backend.
  2. Build `models/User.js` with password pre-save hook:
     ```javascript
     userSchema.pre('save', async function (next) {
       if (!this.isModified('password')) return next();
       this.password = await bcrypt.hash(this.password, 10);
     });
     ```
  3. Create auth controller (`controllers/authController.js`) handling `register`, `login`, and `getMe`.
  4. Create `middleware/authMiddleware.js` to verify `Bearer <token>` in the `Authorization` header.
  5. Build React `AuthContext.jsx` storing token and active user state in memory and `localStorage`.
  6. Build `LoginPage.jsx` and `RegisterPage.jsx` with real-time error handling.
  7. Build `ProtectedRoute.jsx` component redirecting unauthenticated visitors to `/login`.
- **Verification:** Register a user via the React form; inspect MongoDB Compass to confirm password is encrypted with `$2b$` bcrypt hash. Log in and verify Navbar updates to show user avatar and name.

---

### Milestone 6: Blog Ownership, Author Dashboard, Drafts & Publishing
- **Goal:** Enable authenticated authors to create, edit, delete, and manage their own publications.
- **Key Tasks:**
  1. Add authorization checks in `blogController.js`:
     ```javascript
     if (blog.author.toString() !== req.user._id.toString() && req.user.role !== 'admin') {
       return res.status(403).json({ message: 'Forbidden: You do not own this blog' });
     }
     ```
  2. Implement `POST /api/v1/blogs`, `PUT /api/v1/blogs/:id`, `DELETE /api/v1/blogs/:id`.
  3. Implement `GET /api/v1/blogs/my/all` and `GET /api/v1/blogs/my/drafts`.
  4. Build `CreateBlogPage.jsx` and `EditBlogPage.jsx` with status selector (`Draft` vs `Published`).
  5. Build `DashboardPage.jsx` showing the author's published articles and drafts with inline Edit and Delete modals.
- **Verification:** Log in as User A and create a draft. Log in as User B and verify User B cannot view User A's draft or edit their articles.

---

### Milestone 7: Engagement Engine: Comments, Likes & Bookmarks
- **Goal:** Implement relational user interactions stored persistently in MongoDB collections.
- **Key Tasks:**
  1. Build `models/Comment.js`, `models/Like.js`, and `models/Bookmark.js`.
  2. Add compound unique indexes to `Like` and `Bookmark` schemas:
     ```javascript
     likeSchema.index({ blog: 1, user: 1 }, { unique: true });
     bookmarkSchema.index({ blog: 1, user: 1 }, { unique: true });
     ```
  3. Implement endpoints:
     - `POST` & `DELETE /api/v1/blogs/:id/like`
     - `POST`, `PATCH`, `DELETE /api/v1/blogs/:id/comments`
     - `POST` & `DELETE /api/v1/bookmarks/:blogId`
     - `GET /api/v1/bookmarks`
  4. Build interactive `CommentSection` component inside `BlogDetailPage` with delete confirmation.
  5. Implement `LikeButton` with heart fill animation and instant like count updates.
  6. Build `BookmarksPage.jsx` displaying the logged-in user's saved reading list.
- **Verification:** Click like on an article; inspect the `likes` collection in MongoDB. Click like again to verify unlike works without creating duplicate entries.

---

### Milestone 8: Search Engine, Categories, Multi-Filtering & Server-Side Pagination
- **Goal:** Build scalable query mechanisms handling high volumes of articles efficiently.
- **Key Tasks:**
  1. Upgrade `GET /api/v1/blogs` controller to parse query parameters:
     - Search regex: `title` and `content`
     - Category filter: `category` ID or slug
     - Tag filter: `tag`
     - Sort: `newest`, `oldest`, `popular`
     - Pagination: `page` (default 1) and `limit` (default 6)
  2. Return pagination metadata in the response:
     ```json
     {
       "blogs": [ ... ],
       "meta": { "totalBlogs": 32, "totalPages": 6, "currentPage": 1, "hasPrev": false, "hasNext": true }
     }
     ```
  3. Update `BlogListingPage.jsx` with:
     - Live search input with 400ms debounce
     - Category selection pill bar
     - Tag filter sidebar
     - `Pagination` controls (`Prev`, `Next`, active page numbers)
- **Verification:** Create 15 sample blogs. Set limit to 5. Verify page 1 returns 5 articles, page 2 returns the next 5, and Next button disables on page 3.

---

### Milestone 9: Admin CMS Dashboard, RBAC & Content Moderation
- **Goal:** Implement the administrative command center for platform oversight and content moderation.
- **Key Tasks:**
  1. Implement `roleMiddleware.js` verifying `req.user.role === 'admin'`.
  2. Build Admin controllers and routes:
     - `GET /api/v1/admin/stats` (counts of users, blogs, comments, views)
     - `GET /api/v1/admin/users` (list users with status and role toggles)
     - `PATCH /api/v1/admin/users/:id/role` & `status`
     - `GET /api/v1/admin/blogs` (list all blogs including drafts across all authors)
     - `PATCH /api/v1/admin/blogs/:id/feature` (set homepage featured flag)
     - `DELETE /api/v1/admin/blogs/:id` (admin emergency delete)
     - `CRUD /api/v1/categories` (add, edit, remove categories)
  3. Create `AdminRoute.jsx` protected wrapper in React checking `user?.role === 'admin'`.
  4. Build complete `/admin` dashboard views with side navigation:
     - Metrics overview cards
     - Global blog moderation table with search
     - User accounts management table
     - Category taxonomy manager
- **Verification:** Attempt to access `/admin` with a standard user account; confirm access is denied with `403 Forbidden` and redirected to Home. Log in with an admin account and verify full dashboard access.

---

### Milestone 10: Multer File Uploads, Security Hardening, Testing & Cloud Deployment
- **Goal:** Implement local file uploads, harden system security, export Postman tests, and deploy to production.
- **Key Tasks:**
  1. Configure `multer` storage engine with file type validation (`image/jpeg`, `image/png`, `image/webp`) and 5MB size limit:
     ```javascript
     const fileFilter = (req, file, cb) => {
       if (file.mimetype.startsWith('image/')) cb(null, true);
       else cb(new Error('Only image files are permitted!'), false);
     };
     ```
  2. Configure Express to serve static uploads: `app.use('/uploads', express.static('uploads'))`.
  3. Integrate file uploader in `CreateBlogPage` and `ProfilePage`.
  4. Security Hardening:
     - Add `cors` whitelist configuration
     - Add `express-rate-limit` to auth routes
     - Sanitize article HTML output with DOMPurify on the frontend to prevent stored XSS
  5. Author and export comprehensive **Postman Collection** covering all 60+ endpoints.
  6. Deploy:
     - Database: MongoDB Atlas cloud cluster
     - Backend: Render or Railway (configure production environment variables)
     - Frontend: Vercel or Netlify (configure `VITE_API_BASE_URL`)
- **Verification:** Submit a live blog with an uploaded image on the deployed Vercel URL; verify image loads from the live server and data persists across page refreshes.

---

## 9. Security, Performance & Validation Standards

Every student must adhere to the following security guidelines before submitting:

### 9.1 Authentication & Secrets
- **Zero Plaintext Passwords:** Passwords must be hashed using `bcrypt` with a minimum of 10 salt rounds before storage in MongoDB.
- **No Token/Secret Leakage:** Never commit `.env` files to Git. Store `JWT_SECRET`, `MONGO_URI`, and `PORT` exclusively in environment variables.
- **Payload Minimization:** Never return password hashes in API responses (`select: -password`).

### 9.2 Input Sanitization & Attack Prevention
- **Stored XSS Prevention:** Article content created by users must be sanitized on render using `DOMPurify` or safe markdown parsers.
- **NoSQL Injection Guard:** Validate and cast all route parameters (`mongoose.Types.ObjectId.isValid(id)`).
- **CORS Configuration:** Configure CORS to accept requests solely from authorized client origins in production:
  ```javascript
  app.use(cors({ origin: process.env.CLIENT_URL, credentials: true }));
  ```

### 9.3 File Upload Security
- **MIME-Type Whitelist:** Reject any file upload that is not strictly JPEG, PNG, or WebP.
- **File Size Limits:** Strictly enforce 5MB maximum file size for blog covers and 2MB for avatars.
- **Unique Filenames:** Store files with unique timestamps or UUIDs to prevent directory collision attacks.

---

## 10. Repository Directory & File Structure

Students must organize their repository into a clean monorepo architecture:

```
blogsphere/
├── .gitignore
├── README.md                          <-- (This master project specification)
│
├── server/                            <-- Node.js & Express REST Backend
│   ├── .env.example
│   ├── package.json
│   ├── uploads/                       <-- Multer file upload destination
│   │   └── .gitkeep
│   ├── scripts/
│   │   └── seed.js                    <-- Database sample seeder script
│   └── src/
│       ├── server.js                  <-- Express app entry point
│       ├── config/
│       │   └── db.js                  <-- MongoDB Mongoose connection
│       ├── models/
│       │   ├── User.js                <-- User schema & methods
│       │   ├── Blog.js                <-- Blog schema & hooks
│       │   ├── Category.js            <-- Category taxonomy schema
│       │   ├── Comment.js             <-- Discussion comments schema
│       │   ├── Like.js                <-- Likes with compound unique index
│       │   ├── Bookmark.js            <-- Reading list schema
│       │   └── ContactMessage.js      <-- Inquiries schema
│       ├── controllers/
│       │   ├── authController.js      <-- Register, login, me
│       │   ├── userController.js      <-- Profile & avatar management
│       │   ├── blogController.js      <-- Public & author CRUD
│       │   ├── commentController.js   <-- Comments management
│       │   ├── likeController.js      <-- Like & unlike operations
│       │   ├── bookmarkController.js  <-- Bookmark operations
│       │   ├── categoryController.js  <-- Category operations
│       │   ├── adminController.js     <-- Admin metrics & moderation
│       │   └── inquiryController.js   <-- Contact message handling
│       ├── middleware/
│       │   ├── authMiddleware.js      <-- JWT verification
│       │   ├── roleMiddleware.js      <-- RBAC check (admin)
│       │   ├── uploadMiddleware.js    <-- Multer configuration
│       │   └── errorHandler.js        <-- Centralized error middleware
│       ├── routes/
│       │   ├── authRoutes.js
│       │   ├── userRoutes.js
│       │   ├── blogRoutes.js
│       │   ├── commentRoutes.js
│       │   ├── likeRoutes.js
│       │   ├── bookmarkRoutes.js
│       │   ├── categoryRoutes.js
│       │   ├── adminRoutes.js
│       │   └── inquiryRoutes.js
│       └── utils/
│           ├── generateToken.js       <-- JWT signing utility
│           └── slugify.js             <-- URL slug generator
│
├── client/                            <-- React.js + Vite Frontend
│   ├── index.html
│   ├── package.json
│   ├── vite.config.js
│   ├── public/
│   │   └── favicon.svg
│   └── src/
│       ├── main.jsx                   <-- React DOM bootstrap
│       ├── App.jsx                    <-- Router provider & top-level layout
│       ├── assets/                    <-- Static icons and logos
│       ├── styles/
│       │   ├── index.css              <-- Design system & CSS custom variables
│       │   ├── components.css         <-- Shared component classes
│       │   └── dashboard.css          <-- CMS and dashboard layouts
│       ├── context/
│       │   └── AuthContext.jsx        <-- Global auth state & login/logout methods
│       ├── services/
│       │   └── api.js                 <-- Centralized Axios / Fetch instance
│       ├── components/
│       │   ├── layout/
│       │   │   ├── Navbar.jsx         <-- Responsive navigation bar
│       │   │   ├── Footer.jsx         <-- Multi-column footer
│       │   │   └── Layout.jsx         <-- Main page outlet shell
│       │   ├── common/
│       │   │   ├── Button.jsx         <-- Reusable styled button
│       │   │   ├── Badge.jsx          <-- Category / status pill tag
│       │   │   ├── LoadingSpinner.jsx <-- Animated loading state
│       │   │   ├── ErrorMessage.jsx   <-- Accessible error alert
│       │   │   ├── EmptyState.jsx     <-- Graphic empty state placeholder
│       │   │   └── Modal.jsx          <-- Accessible confirmation modal
│       │   ├── blog/
│       │   │   ├── BlogCard.jsx       <-- Editorial article preview card
│       │   │   ├── BlogList.jsx       <-- Responsive card grid
│       │   │   ├── FeaturedCard.jsx   <-- Hero featured article card
│       │   │   ├── SearchBar.jsx      <-- Live search input
│       │   │   ├── CategoryFilter.jsx <-- Filter pills bar
│       │   │   ├── Pagination.jsx     <-- Server-side page navigation
│       │   │   ├── CommentSection.jsx <-- Comment feed & input
│       │   │   ├── LikeButton.jsx     <-- Animated like toggle
│       │   │   └── BookmarkButton.jsx <-- Reading list toggle
│       │   └── auth/
│       │       ├── ProtectedRoute.jsx <-- Guards authenticated routes
│       │       └── AdminRoute.jsx     <-- Guards admin-only routes
│       └── pages/
│           ├── HomePage.jsx           <-- Landing page with hero & feeds
│           ├── BlogListingPage.jsx    <-- Search & filter catalog
│           ├── BlogDetailPage.jsx     <-- Full article reader
│           ├── AuthorProfilePage.jsx  <-- Public author portfolio
│           ├── AboutContactPage.jsx   <-- About & contact inquiry form
│           ├── LoginPage.jsx          <-- User login
│           ├── RegisterPage.jsx       <-- User registration
│           ├── DashboardPage.jsx      <-- Author personal management
│           ├── CreateBlogPage.jsx     <-- Article publishing studio
│           ├── EditBlogPage.jsx       <-- Article update studio
│           ├── BookmarksPage.jsx      <-- Personal reading list
│           ├── ProfilePage.jsx        <-- Settings & avatar upload
│           ├── AdminDashboardPage.jsx <-- CMS analytics & control center
│           └── NotFoundPage.jsx       <-- 404 page
│
└── docs/                              <-- Documentation & Test Artifacts
    ├── BlogSphere_Postman.json        <-- Exported Postman API collection
    └── deployment_guide.md            <-- Deployment verification notes
```

---

## 11. Local Development & Environment Setup Guide

### 11.1 Prerequisites
- **Node.js:** v18.0.0 or higher ([Download Node.js](https://nodejs.org/))
- **NPM:** v9.0.0 or higher
- **MongoDB:** MongoDB Community Server installed locally OR a free MongoDB Atlas Cloud Cluster account ([MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- **Git:** Git CLI installed ([Download Git](https://git-scm.com/))
- **Postman:** Recommended for API verification ([Download Postman](https://www.postman.com/))

---

### 11.2 Step-by-Step Installation

#### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/blogsphere.git
cd blogsphere
```

#### Step 2: Configure Server Environment Variables
Navigate into `/server` and create a `.env` file based on `.env.example`:
```bash
cd server
copy .env.example .env     # On Windows Command Prompt / PowerShell
# or: cp .env.example .env  # On macOS / Linux
```

Populate `server/.env` with your credentials:
```env
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/blogsphere?retryWrites=true&w=majority
JWT_SECRET=super_secret_jwt_passphrase_key_blogsphere_2026
JWT_EXPIRE=7d
CLIENT_URL=http://localhost:5173
```

#### Step 3: Install Server Dependencies & Seed Data
```bash
npm install
npm run seed     # Seeds initial categories and sample articles into MongoDB
npm run dev      # Launches Express server on http://localhost:5000
```

#### Step 4: Configure & Launch React Client
In a separate terminal window:
```bash
cd ../client
copy .env.example .env     # (If configured)
npm install
npm run dev                # Launches Vite development server on http://localhost:5173
```

Open your browser and navigate to `http://localhost:5173`. You should see the BlogSphere home page populated with your seeded articles.

---

## 12. Student Evaluation Rubric (100-Point Scale)

Your project will be evaluated on the following 10 criteria by the technical jury:

| Category | Max Score | Evaluation Criteria |
| :--- | :---: | :--- |
| **1. UI/UX Design & Component Architecture** | **10 pts** | Clean editorial aesthetic, cohesive typography, responsive across mobile/tablet/desktop, reusable components, loading and error states. |
| **2. Client Routing & Form Handling** | **10 pts** | Proper React Router v6 layout with nested routes, client-side input validation, feedback banners, and error handling. |
| **3. Express API Architecture** | **15 pts** | Modular MVC structure (controllers, routes, services), clean standard JSON responses, centralized error middleware, and consistent HTTP status codes. |
| **4. MongoDB & Mongoose Modeling** | **10 pts** | Schema design with references (`ref`), compound unique indexes for likes and bookmarks, slug generation, and lean queries. |
| **5. Core Blog CRUD & Draft Workflows** | **15 pts** | Complete create, read, update, delete functionality; draft vs published status workflow; author ownership checks. |
| **6. Authentication & Role-Based Access Control** | **15 pts** | Secure JWT issuance and verification, salted bcrypt password hashing (min 10 rounds), protected React routes, and `/admin` RBAC isolation. |
| **7. Search, Pagination & Taxonomy Filters** | **5 pts** | Functional search bar with debouncing, category and tag filters, sort controls, and server-side pagination with accurate page metadata. |
| **8. Engagement Engine (Likes, Comments, Bookmarks)** | **5 pts** | MongoDB-persisted likes (preventing duplicates), nested comments with author deletion, and reading list bookmark persistence. |
| **9. Security, Validation & File Handling** | **5 pts** | Multer file type and size validation, sanitization against XSS, CORS protection, and secure environment variable separation. |
| **10. Testing, Git Workflow & Deployment** | **10 pts** | Comprehensive Postman collection covering 60+ endpoints, clean Git commit history, comprehensive README, and live cloud deployment. |
| **TOTAL SCORE** | **100 pts** | **Minimum Passing Grade:** 70 / 100. **Distinction:** 90+ / 100. |

---

## 13. Final Submission, Demo & Presentation Checklist

Before submitting your capstone project, ensure every item on this checklist is completed:

- [ ] **GitHub Repository:**
  - [ ] Public GitHub repository with clean, descriptive commit messages tracking progress milestone-by-milestone.
  - [ ] No `.env` files, `node_modules/`, or large binary files committed to Git.
  - [ ] Root `README.md` containing clear local setup instructions and deployed links.
- [ ] **Database Integrity:**
  - [ ] MongoDB Atlas cluster configured with network access whitelist (`0.0.0.0/0` for cloud deployment).
  - [ ] Working database seed script (`npm run seed`) capable of populating categories and initial sample articles on a fresh database.
- [ ] **REST API & Postman Verification:**
  - [ ] All 60+ endpoints defined in Section 7 implemented and responding with standard JSON envelopes.
  - [ ] Exported Postman Collection JSON placed in `/docs/BlogSphere_Postman.json`.
- [ ] **Authentication & Security:**
  - [ ] Passwords stored strictly as bcrypt hashes in MongoDB.
  - [ ] Normal registered users cannot access `/admin` or edit other users' content.
  - [ ] Unauthenticated guests are prevented from posting comments, liking, or bookmarking.
- [ ] **Cloud Deployment:**
  - [ ] Live Backend deployed on Render, Railway, or Heroku with healthy `/api/v1/health` response.
  - [ ] Live Frontend deployed on Vercel or Netlify with working client-side routing (including SPA redirect rules).
- [ ] **5-Minute Technical Demo:**
  - [ ] Be prepared to present a 5-minute walkthrough showing:
    1. Guest browsing, search, and reading experience.
    2. User registration, login, and author dashboard.
    3. Creating and publishing a new blog with an image.
    4. Adding comments, likes, and bookmarks.
    5. Logging into the Admin CMS Dashboard to moderate content and review system metrics.

---

*BlogSphere Capstone Specification • Prepared for Full Stack Engineering Students • Version 2.4*
