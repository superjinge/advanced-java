# AGENTS.md

This file provides guidance for AI agents working in this repository.

## Project Overview

This is a pure Markdown documentation site — an advanced Java engineering knowledge base ("互联网 Java 工程师进阶知识完全扫盲") covering system design topics: high concurrency, distributed systems, high availability, and microservices. It is rendered in the browser using [Docsify](https://docsify.js.org/) with no build step.

**There is no source code.** All content is Markdown articles, primarily written in Simplified Chinese.

## Repository Structure

```
/
├── index.html              # Docsify app entry point (CDN-loaded, no build needed)
├── README.md               # Main navigation / table of contents
└── docs/
    ├── high-concurrency/   # Redis, MQ, Elasticsearch, DB sharding, etc.
    ├── distributed-system/ # Dubbo, ZooKeeper, distributed transactions, etc.
    ├── high-availability/  # Hystrix, circuit breakers, rate limiting, etc.
    ├── micro-services/     # Microservices, Spring Cloud, etc.
    ├── from-readers/       # Community-contributed articles
    └── extra-page/         # Cover page, tips, and supplemental pages
```

Each subdirectory under `docs/` has its own `README.md` that serves as its section introduction.

## Running Locally

No build step is required. Serve the repo root with any static HTTP server:

```bash
# Using docsify-cli (recommended)
npm install -g docsify-cli
docsify serve .

# Or using npx
npx serve .

# Or using Python
python3 -m http.server 3000
```

Then open `http://localhost:3000` (or whichever port is used) in a browser.

## Content Conventions

- **Language:** All articles are written in Simplified Chinese.
- **File naming:** Use kebab-case descriptive names (e.g., `redis-cluster.md`, `distributed-transaction.md`).
- **Community articles:** Files contributed by readers are prefixed with the author's GitHub username (e.g., `huifer-how-to-limit-current.md`).
- **Navigation:** When adding a new article, add a corresponding link in the parent section's `README.md` and in the top-level `README.md`.
- **Code examples:** Inline code blocks within Markdown are rendered with Prism.js syntax highlighting via `index.html`. No separate code files are needed.

## No Tests or Linting

There are no automated tests or linters configured in this repository. After making changes, verify correctness by serving the site locally and reviewing the rendered output in a browser.

## Making Changes

1. **Editing existing articles:** Edit the relevant `.md` file directly under `docs/`.
2. **Adding a new article:** Create the `.md` file in the appropriate `docs/` subdirectory, then add a link to it in the section's `README.md` and in the top-level `README.md`.
3. **Changing site configuration:** Edit `index.html` (Docsify plugins, theme, repo link, etc.).
4. **No build or compilation step is needed after any change.**
