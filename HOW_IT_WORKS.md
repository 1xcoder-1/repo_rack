# How RepoRack Works 🔍

RepoRack is a modern star history tracker built for speed and aesthetics. This document explains the technical implementation and the logic behind our charts.

## 🛠 Tech Stack
-   **Frontend**: Next.js 16 (App Router)
-   **Styling**: Tailwind CSS v4 with custom font triggers
-   **Charts**: [Recharts](https://recharts.org/) for high-performance rendering
-   **State**: URL-synced state using `nuqs`, allowing shareable links
-   **API**: GitHub REST API (v3)

## 📊 The Data Pipeline

### 1. Smart Sampling
Fetching every single star for a repository with 200k+ stars is slow and would quickly hit GitHub's API rate limits. To solve this, RepoRack uses **Smart Sampling**:
-   GitHub allows fetching up to 40,000 stargazers (400 pages of 100).
-   For repos with < 40,000 stars, we sample ~20-40 specific pages based on the repo's age and star density.
-   For repos with > 40,000 stars, GitHub stops giving us data.

### 2. Tail Interpolation (S-Curve)
When a repo exceeds 40,000 stars, there is a "blind spot" between the 40,000th star and the current star count.
-   We fetch the **current star count** from the main repo info API.
-   We use a **Smoothstep (S-curve)** algorithm to interpolate the missing data points.
-   This ensures the chart looks natural and reflects the actual current growth without showing a "broken" line.

### 3. Caching Strategy
-   **Client-side**: We use `localStorage` to cache repo data for 24 hours. This makes the UI feel instant when you return to a previously viewed repo.
-   **Server-side**: API routes use `s-maxage` headers to signal Vercel's Edge Network to cache the results, reducing the load on GitHub's API.

## 🎨 Theme Engine
RepoRack features 15+ custom themes.
-   Each theme is defined as a `ChartTheme` object in `lib/themes.ts`.
-   Themes control backgrounds, grid colors, line colors, and even typography (e.g., the **8-Bit** theme loads Google Fonts' *Press Start 2P*).
-   Themes are applied dynamically to the `Recharts` components via a React context provider.

## 🚀 API Rate Limits
GitHub limits unauthenticated requests to 60 per hour.
-   RepoRack uses a `GITHUB_TOKEN` on the server to increase this limit to 5,000 per hour.
-   If you're running the app locally, be sure to add your own token to `.env.local` to avoid rate limiting during development.

## 🖼 Image Export
The PNG export functionality uses `html-to-image` to capture the chart area at 2x resolution, ensuring crisp images for sharing on social media or in presentations.
