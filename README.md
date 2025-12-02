🌟 AccountableAI — AI-Powered Weekly Planning & Accountability

AccountableAI is a Next.js SaaS app designed to help you plan your week, compare planned vs. actual time, and receive AI-driven coaching based on your habits.
It uses:

Next.js 14 (App Router)

Clerk for authentication

Supabase for database + RLS storage

OpenAI for weekly coaching, summaries, and insights

shadcn/ui for design

Recharts for visual analytics

dnd-kit for drag-and-drop goal prioritization

Lottie + Framer Motion for animations

A full onboarding tour, achievements, and XP leveling system

🚀 Features
🧠 AI Coaching

Compares planned vs actual time

Generates weekly summaries

Learns your habits (coach memory system)

Adjusts tone and advice to your patterns

Optional voice assistant mode

📅 Weekly Planning

Add weekly goals

Reorder goals with drag & drop

Assign target hours

Upload calendar screenshots (OCR-ready pipeline)

📊 Analytics

“Planned vs. Actual” bar charts

Timeline view (Gantt-like)

Focus scores

Streaks and performance metrics

🏅 Gamification

XP + Level system

Achievements & badges

Streak boosts

Level-up animations

🎓 Smart Onboarding

Contextual tooltips

Progress bar

Animated coach avatar

Voice-enabled tutorial

🧩 Tech Stack
Area	Technology
Frontend	Next.js 14 (App Router), React, TypeScript
UI	TailwindCSS, shadcn/ui, Radix UI
Drag & Drop	dnd-kit
Charts	Recharts
Animations	Framer Motion, Lottie
Auth	Clerk
Backend	Next.js Route Handlers
Database	Supabase (Postgres + RLS)
AI	OpenAI (GPT-4.1, GPT-4.1-mini, TTS)
📦 Installation

Clone the repo:

git clone https://github.com/musikito/accountableai.git
cd accountableai


Install dependencies:

pnpm install

🔐 Environment Variables

Create .env.local:

# Clerk
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_live_xxxxx
CLERK_SECRET_KEY=sk_live_xxxxx

# Supabase
NEXT_PUBLIC_SUPABASE_URL=https://YOUR_PROJECT.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=public_anon_key
SUPABASE_SERVICE_ROLE_KEY=service_role_key

# OpenAI
OPENAI_API_KEY=sk-...

# Misc
NODE_ENV=development

🗄️ Database Schema (Supabase)

Create through migration:

supabase/migrations/0001_init.sql


Includes tables:

profiles

weeks

goals

time_blocks

weekly_summaries

coach_memory

achievements

user_achievements

With support for:

XP & leveling

AI feedback memory

Weekly summaries

Time tracking

Goal planning

▶️ Development

Start local dev server:

pnpm dev


Visit:

http://localhost:3000


Sign up via Clerk → redirected to dashboard.

📘 Project Structure
src/
  app/
    dashboard/
    weeks/
    api/
      weeks/
        [weekId]/
          summary/
      onboarding/
  components/
    goals/
    weekly/
    onboarding/
    achievements/
    profile/
  context/
    onboarding-context.tsx
  lib/
    supabase/
    coachMemory.ts
    xp.ts
    achievements.ts

public/
  lottie/
  coach-avatar.gif

🛠️ Core Components
GoalSetter

Drag-and-drop goal tool with local + Supabase sync.

WeeklyComparisonChart

Recharts-based bar chart showing planned vs actual.

OnboardingPopover

shadcn/Radix-powered guided onboarding bubbles.

OnboardingCoach

Animated avatar that reacts to onboarding steps.

OnboardingVoice

OpenAI-backed push-to-talk voice guidance.

XPBar

Level and experience progress display.

AchievementBadge

Shows earned achievements.

🤖 AI Integration
Weekly Summary AI

Route:

/api/weeks/[weekId]/summary


Uses:

Goals

Time blocks

User memory

XP & streaks

OpenAI coaching model

Generates:

AI text summary

Coach reaction

Performance insights

Updates XP & achievements

Voice Assistant AI

Route:

/api/onboarding/voice-text


Features:

Audio transcription

JSON action parsing (next/repeat/none)

TTS audio output

🧠 Coach Memory System

Stores:

Behavioral patterns

Productivity rhythms

Overplanning tendencies

Best focus days

Personal affirmations

Goal category bias

Used every week to adjust AI coaching.

🏆 Achievements + XP System

Earn XP for:

Completing onboarding

Weekly reviews

Streaks

Focus scores

Achievements unlocked

Drag-and-drop mastery

Health consistency

Goal completion

XP increases level, triggering a level-up animation and a celebratory coach message.

📸 Screenshots

(Add your generated images here.)

🌐 Deployment

Deploy easily with Vercel:

vercel


Make sure to add env variables to Vercel dashboard.

Supabase stays managed.

Clerk requires allowed domain setup.

📜 License

MIT License.
See LICENSE.

💛 Support

If you want additional features:

Google Calendar sync

OCR calendar parsing

Native mobile app (Expo)

Team accountability dashboards

AI multi-week planning

Custom coach personalities

Deep coach memory with embeddings

Open an issue or DM me!