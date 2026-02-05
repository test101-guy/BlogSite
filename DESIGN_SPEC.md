# Educational Content Platform — Product + UX + Architecture Spec

## 1) Product Vision
A modern, scalable educational content platform that launches as a **blog + eBook marketplace + video learning site** and expands into **tutors, courses, and bookings**. The product targets **children and general learners** with a **kid-friendly yet professional** experience, strong discoverability, and monetization readiness.

**Core principles**
- **Content-first**: quick discovery and consumption.
- **Safety + trust**: secure authentication, parental confidence, and transparent payments.
- **Scalable**: modular architecture to support future learning products.
- **Mobile-first**: fast, accessible, and responsive.

---

## 2) User Roles & Access

### Guest (Not logged in)
- Explore public content (blog and public videos/eBooks).
- See marketing pages and conversion CTAs.
- Must log in to purchase/download paid items.

### Registered User (Learner/Reader)
- Full access to purchased eBooks and premium videos.
- Save/bookmark content.
- Personalized dashboard and notifications.

### Admin (Separate login & dashboard)
- Dedicated admin login path and session.
- Manage content, users, payments, categories, and site settings.

---

## 3) Information Architecture & Navigation Flow

### Primary navigation (public)
- **Home**
- **Blog**
- **eBooks**
- **Videos**
- **About**
- **Contact**
- **Login / Create Account**

### Authenticated user navigation
- **Dashboard Home**
- **My Purchases**
- **Saved Content**
- **Profile**
- **Notifications**
- **Logout**

### Admin navigation (separate)
- **Admin Dashboard**
- **Content**
  - Articles
  - eBooks
  - Videos
- **Users**
- **Payments & Revenue**
- **Settings**
- **Logout**

### High-level flow
1. **Guest visits Home → explores content → clicks CTA**
2. **Login/Sign up → Dashboard → purchases or unlocks content**
3. **Admin login → content management → publish & feature**

---

## 4) UI/UX Design System

### Visual tone
**Clean, modern, educational**, bright but calm colors, friendly but professional.

### Core UI Elements
- **Card-based layout** for content previews.
- **Large, readable typography** (accessible for children).
- **Consistent CTAs** (primary/secondary buttons).
- **Friendly iconography** (books, video, star, rocket).

### Component Set (Reusable)
**Navigation**
- Top App Bar
- Sticky secondary nav for category filters

**Content**
- Article Card
- eBook Card
- Video Card
- Featured Banner
- Category Chips/Tags

**Commerce**
- Price badge
- Locked/Unlocked badge
- Buy/Download button

**Utility**
- Search bar
- Filter dropdowns
- Pagination/infinite scroll
- Toast notifications
- Empty states

**Forms**
- Input fields with help text
- Password strength indicator
- Consent checkbox

---

## 5) Public/Marketing Pages — UX & Layout

### 🏠 Home Page (Conversion & Discovery)
**Sections (Top → Bottom)**
1. **Hero**
   - Headline: “Learn, Read & Grow with Fun Educational Content”
   - Subtext: Safe, curated content for kids and learners.
   - CTAs: Read Articles, Buy eBooks, Watch Videos, Create Account
2. **Featured Blog Articles** (carousel or grid)
3. **Featured eBooks** (cards with prices)
4. **Featured Videos** (thumbnails + duration)
5. **Categories**
   - Blog / eBooks / Videos
6. **Testimonials / Trust Indicators**
7. **Newsletter Signup**
8. **Footer**
   - About, Contact, Policies, Social links

### 📖 Blog Listing Page
**Key components**
- Search bar + category filter
- Featured article highlight (top)
- Grid/list of articles
- Pagination or infinite scroll

### 📝 Blog Article Page
**Layout**
- Cover image hero
- Title, author, date, read time
- Rich text body with inline images
- Share buttons
- Related articles section

### 📚 eBooks Store Page
**Key components**
- Filters (price, category, free/paid)
- Grid of eBook cards
- Price badge + “View details”

### 📕 eBook Details Page
- Large cover preview
- Full description
- What you’ll learn (bullet list)
- Price + Buy/Download button
- Login required for purchase
- Related eBooks

### 🎥 Videos Library Page
- Video thumbnails with duration
- Categories filter
- Locked/Unlocked badges
- Filter by free/paid

### ▶️ Video Watch Page
- Video player (responsive)
- Title + description
- Notes/resources section
- Related videos
- Access control for premium videos

### ℹ️ About Page
- Mission, vision, target audience
- Why this platform exists

### 📞 Contact Page
- Contact form + email
- Social links

---

## 6) Authentication Pages

### 🔐 Login
- Email + password
- Social login (optional)
- Forgot password link

### ✍️ Sign Up
- Name, email, password, confirm
- Terms checkbox
- Email verification notice

### 🔁 Forgot / Reset Password
- Email input → reset link
- New password + confirm

---

## 7) User Dashboard (Authenticated)

### 🧭 Dashboard Home
**Widgets**
- Welcome message
- Recently viewed content
- Purchased eBooks
- Saved articles/videos

### 📦 My Purchases
- eBook list with download buttons
- Payment history

### ❤️ Saved/Bookmarked Content
- Tabs for Articles / Videos / eBooks

### 👤 Profile Page
- Edit profile, password change, profile picture

### 🔔 Notifications
- Purchase confirmations
- New content alerts

---

## 8) Admin System (Separate Login & Dashboard)

### 🔐 Admin Login Page
- Separate URL (e.g., `/admin/login`)
- Secure access only for admin role

### 📊 Admin Dashboard Overview
- Total users, articles, eBooks, videos
- Revenue summary
- Recent activity feed

### 📝 Content Management
**Articles**
- Create/edit/delete
- Rich text editor
- Draft/publish status

**eBooks**
- Upload PDF
- Price, free/paid toggle
- Category assignment
- Download tracking

**Videos**
- Upload or embed
- Free/paid toggle
- Categories + visibility

### 👥 User Management
- List/search users
- Block/unblock
- View purchases
- Role assignment (future)

### 💳 Payments & Revenue
- Transactions list
- Revenue analytics
- Export CSV

### ⚙️ Settings
- Site name & branding
- Featured homepage content
- Category management
- Email templates

---

## 9) System & Tech Requirements

### Frontend
- **Next.js / React** (SSR for SEO)
- **Tailwind CSS** or **MUI** for scalable UI
- **Responsive design** (mobile-first)

### Backend
- **Node.js + PostgreSQL** (or Supabase)
- **REST or GraphQL API**
- File storage: **S3 / Cloudinary**

### Authentication & Security
- JWT or Supabase Auth
- Role-based access control (RBAC)
- Secure payment webhooks

### Monetization
- Stripe + Flutterwave
- Paid content gating
- Purchase history tracking

### SEO & Performance
- Schema markup for articles/videos
- Optimized media and lazy loading
- Server-side rendering

---

## 10) Future Expansion (Built into Structure)
- Tutor profiles
- Course creation
- Bookings & scheduling
- Certificates
- Multi-language support
- Mobile app

---

## 11) Production-Ready Structure (Suggested)

```
apps/
  web/                 # user-facing app
  admin/               # separate admin dashboard
packages/
  ui/                  # shared UI library
  auth/                # auth logic
  payments/            # stripe/flutterwave wrapper
  content/             # content service (blog, ebooks, videos)
```

---

## 12) Delivery Summary
This design provides a **clean, content-driven experience** with **clear user/admin separation**, **growth-ready architecture**, and **modern UI components** optimized for learners and children.
