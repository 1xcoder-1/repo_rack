# Contributing to RepoRack 🚀

First off, thank you for considering contributing to RepoRack! It's people like you that make RepoRack such a great tool.

## Code of Conduct

By participating in this project, you are expected to uphold our Code of Conduct:
- Use welcoming and inclusive language
- Be respectful of differing viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on what is best for the community

## How Can I Contribute?

### Reporting Bugs
Before creating a bug report, please check the existing issues to see if the problem has already been reported. When creating a bug report, include:
- A clear and descriptive title
- Steps to reproduce the bug
- Expected vs. Actual behavior
- Screenshots if applicable
- Your environment (browser, OS)

### Suggesting Enhancements
Enhancement suggestions are tracked as GitHub issues. When suggesting an enhancement:
- Use a clear and descriptive title
- Provide a step-by-step description of the suggested enhancement
- Explain why this enhancement would be useful to RepoRack users
- List any technical details or design sketches if you have them

### Your First Code Contribution
1.  **Fork the repo** and create your branch from `main`.
2.  **Environment Setup**:
    -   Install dependencies: `pnpm install`
    -   Copy `.env.example` to `.env.local` and add your `GITHUB_TOKEN`
    -   Start dev server: `pnpm dev`
3.  **Code Style**:
    -   We use [Biome](https://biomejs.dev/) for formatting and linting.
    -   Run `pnpm fix` before committing to ensure everything is clean.
4.  **Commit Messages**:
    -   Use descriptive commit messages. We follow Conventional Commits (feat, fix, refactor, docs, chore).
5.  **Pull Request**:
    -   Submit your PR against the `main` branch.
    -   Describe your changes in detail in the PR description.

## Tech Stack
-   **Framework**: Next.js 16 (App Router)
-   **Styling**: Tailwind CSS v4
-   **Charts**: Recharts
-   **State Management**: `nuqs` for URL-based state
-   **Icons**: Phosphor Icons

## Testing
Currently, we rely on manual testing for UI components. Please ensure you test your changes across different themes (especially Neon, 8-Bit, and Minimal).

## Questions?
Feel free to open an issue with the "question" label!

Happy coding! 🌟
