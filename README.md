# Website Builder Backend

A Node.js + TypeScript backend that accepts website prompts (for example, via WhatsApp), generates a GitHub repository for the site, and deploys it to Vercel.


## Example WhatsApp Prompt

```
Create a one page with lightning theme color palette with only one section with a text saying "KACHOWW
```

![WhatsApp Image 2026-03-04 at 10 40 28 AM](https://github.com/user-attachments/assets/e279d734-21a6-4d16-974e-535939ec526a)

The backend will parse the prompt, select a skill template (e.g. portfolio), generate files via the LLM, create a GitHub repo, and trigger a Vercel deployment.


<img width="900" height="736" alt="screenshot-20260304-051151Z-selected" src="https://github.com/user-attachments/assets/8ef7f567-607f-48b8-8e7f-90c2e16de8bd" />

## What it does

- Accepts incoming prompts (webhook) describing a website.
- Uses an LLM-driven generator to produce site files and a repo layout.
- Creates a GitHub repository and pushes generated files.
- Triggers a Vercel deployment using `VERCEL_TOKEN` and reports status.

## Quick Start

1. Install dependencies:

```bash
pnpm install
```

2. Create a `.env` file (see below) then run in development:

```bash
pnpm dev
```

## Environment

Add a `.env` file with these variables (adjust to your needs):


- `GITHUB_TOKEN` - Personal Access Token with repo permissions
- `GITHUB_OWNER` - Owner (username or org) where repos will be created
- `GITHUB_OWNER_TYPE` - `user` or `org` (defaults to `user`)
- `GITHUB_REPO_PREFIX` - prefix for generated repo names (default `ai-site-`)
- `PORT` - optional (default 3000)
- `ANTHROPIC_API_KEY` - Anthropic API key
- `VERCEL_TOKEN` - Vercel tokent for deploying repos
- `APP_SECRET` - Whatsapp App secret
- `WHATSAPP_PHONE_NUMBER_ID`
- `WHATSAPP_ACCESS_TOKEN`
- `WHATSAPP_VERIFY_TOKEN`
- `PORT` - Port number to run the backend

