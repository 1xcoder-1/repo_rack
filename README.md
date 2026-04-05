# <img src="public/repostars-logo.png" width="36" height="36" alt="RepoRack Logo" /> RepoRack

**Compare, Track, and Visualize GitHub Star History with Style.**


RepoRack is a modern, high-performance star history tracker for GitHub. Unlike standard trackers, RepoRack focuses on **visual excellence**, offering 15+ beautifully curated themes (from **8-Bit Retro** to **Electric Neon**) and side-by-side comparisons for up to 5 repositories.



## ✨ Key Features

-   🎨 **15+ Themes** — Dark, Light, Neon, Minimal, 8-Bit, Sunset, Ocean, Candy, Forest, Terminal, Lava, Arctic, Copper, Synthwave, Sakura.
-   📊 **Compare Repos** — Add up to 5 repositories to compare their growth side-by-side on a single chart.
-   ⚡ **Smart Sampling** — High-speed binning and interpolation—fast even for repos with 200K+ stars.
-   🔗 **Shareable Links** — URL search params sync perfectly; copy a link and your repos + theme are baked in.
-   🖼 **Export PNG** — High-resolution (2x) chart export for social media, blogs, or presentations.
-   🚀 **Edge-Ready** — Built with Next.js 16 and optimized for Vercel's global CDN with 24h caching.

## 🛠 Tech Stack

-   **Framework**: [Next.js 16](https://nextjs.org/) (App Router)
-   **Styling**: [Tailwind CSS v4](https://tailwindcss.com/)
-   **Charts**: [Recharts](https://recharts.org/)
-   **State Management**: [nuqs](https://nuqs.47ng.com/) for URL state
-   **Icons**: [Phosphor Icons](https://phosphoricons.com/)
-   **Components**: [shadcn/ui](https://ui.shadcn.com/)

## 🚀 Getting Started

### Prerequisites
-   Node.js 20+
-   pnpm (recommended)

### Installation
1.  **Clone the repository**:
    ```bash
    git clone https://github.com/1xcoder-1/repo_rack.git
    cd repostars
    ```

2.  **Install dependencies**:
    ```bash
    pnpm install
    ```

3.  **Local Environment**:
    Create a `.env.local` file and add your GitHub token to increase API rate limits (optional but recommended):
    ```env
    GITHUB_TOKEN=your_github_pat_here
    ```

4.  **Run Development Server**:
    ```bash
    pnpm dev
    ```
    Open [http://localhost:3000](http://localhost:3000) to see the results.

## 📖 Learn More
-   [How It Works](HOW_IT_WORKS.md) — Technical details, sampling logic, and interpolation.
-   [Contributing](CONTRIBUTING.md) — Help us make RepoRack better!

