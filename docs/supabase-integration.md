# UntreX × Supabase Integration Guide

## Overview

UntreX is a modern storytelling platform that enables users to create, organize, and preserve meaningful stories with rich media, privacy controls, and a distraction-free reading experience.

Supabase powers the core backend infrastructure of UntreX by providing secure authentication, a scalable PostgreSQL database, object storage for media, real-time capabilities, and enterprise-grade security.

---

# Features

UntreX integrates with the following Supabase services:

- **Supabase Authentication**
  - Secure user authentication
  - Session management
  - Email-based authentication
  - OAuth-ready architecture

- **PostgreSQL Database**
  - User profiles
  - Stories
  - Story chapters
  - Media metadata
  - User settings

- **Supabase Storage**
  - Profile images
  - Story images
  - Story videos
  - Media asset management

- **Realtime**
  - Live updates
  - Instant synchronization
  - Future collaborative features

- **Row Level Security (RLS)**
  - Secure data isolation
  - User-level access control
  - Protected database operations

---

# Architecture

```
Client Application
        │
        ▼
 Supabase Authentication
        │
        ▼
 PostgreSQL Database
        │
 ┌──────┴────────┐
 │               │
 ▼               ▼
Storage      Realtime
```

---

# Getting Started

## Requirements

- Node.js 18+
- Supabase Project
- Supabase Account

---

## Install SDK

```bash
npm install @supabase/supabase-js
```

---

## Environment Variables

Create a `.env.local` file.

```env
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-public-anon-key
```

> **Important:** Never expose your Service Role Key or any private credentials in client-side applications.

---

## Initialize Supabase

```typescript
import { createClient } from "@supabase/supabase-js";

export const supabase = createClient(
  process.env.NEXT_PUBLIC_SUPABASE_URL!,
  process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!
);
```

---

# Authentication

UntreX uses Supabase Authentication to securely manage user accounts and sessions.

Current authentication capabilities include:

- Email & Password Authentication
- Secure Session Management
- Password Recovery
- Future OAuth Provider Support

---

# Database

The PostgreSQL database stores application data including:

- User Profiles
- Stories
- Story Chapters
- Media References
- User Preferences

All sensitive operations are protected using Row Level Security (RLS) policies.

---

# Storage

Supabase Storage is used for managing user-generated content.

Supported media includes:

- Images
- Videos
- Profile Pictures

Storage buckets are protected with access policies to ensure users can only access authorized content.

---

# Security

Security is a core part of the UntreX platform.

Implemented security features include:

- Row Level Security (RLS)
- Secure Authentication
- HTTPS Communication
- Protected Storage Policies
- Environment Variable Management

No sensitive credentials or secret keys are exposed in client-side applications.

---

# Scalability

Supabase provides the scalable backend infrastructure required to support growing user communities while maintaining performance, reliability, and security.

The architecture is designed to support future expansion without significant infrastructure changes.

---

# Future Enhancements

Planned improvements include:

- Edge Functions
- AI-powered Story Search
- Semantic Search
- Advanced Analytics
- Enhanced Realtime Collaboration
- Additional Authentication Providers

---

# Resources

- Website: https://untrex.in
- Documentation Repository: https://github.com/untre-x/untrex-docs

---

# Support

For questions, feedback, or technical assistance, please contact:

**Email:** support@untrex.in

---

# License

MIT License
