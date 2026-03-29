# Skill Vault

**Your personal library for Claude Code skills.**

[Lea esto en Español](README.es.md)

---

## What is this?

Imagine you have a big toy box, but instead of toys, it holds **skills** — special abilities that make Claude Code smarter.

People are sharing thousands of skills online every day. The problem? They're scattered everywhere. You find one on GitHub, another on skills.sh, another someone shared on X... and then you forget where you saved them. Or worse — some of them might be harmful.

**Skill Vault** is your organized, safe toy box for skills. It does three things:

1. **Saves and organizes** your skills into labeled folders
2. **Checks each skill for danger** before saving it (like a security guard for your computer)
3. **Helps you find the right skill** when you're building something

That's it. Clone it, open it with Claude, and start collecting.

---

## Getting Started

```bash
git clone https://github.com/Hainrixz/skill-vault.git
cd skill-vault
claude
```

No installs. No setup. No dependencies. Just open it and go.

---

## How It Works

When you open this project with Claude Code, the **Vault Master** agent takes over. Think of it as your personal librarian who:

- **Accepts skills** from anywhere — paste a URL, paste the content, or just tell it a name
- **Analyzes each skill** through a 13-point security checklist and rates it: SAFE, CAUTION, or DANGEROUS
- **Files it** in the right category folder automatically
- **Finds skills for you** when you describe what you're building

### Commands

| Command | What it does |
|---------|-------------|
| `/vault-add` | Save a new skill (from URL, paste, or name) |
| `/vault-search` | Search your vault by keyword |
| `/vault-recommend` | Describe your project, get matching skills |
| `/vault-discover` | Find new skills from the internet |
| `/vault-list` | See everything in your vault |
| `/vault-stats` | Vault stats + health check |
| `/vault-remove` | Remove a skill |

---

## Folder Structure

Skills are saved in category folders. Each skill gets its own file with metadata, security analysis, install instructions, and the original content preserved.

```
categories/
├── automation/          # Browser bots, scripts, task runners
├── code-quality/        # Linting, refactoring, reviews
├── design-ui/           # UI components, design systems, CSS
├── devops-deploy/       # Docker, CI/CD, infrastructure
├── documentation/       # READMEs, API docs, changelogs
├── organization/        # Project management, planning
├── productivity/        # Text tools, meeting notes, workflows
├── research/            # Web research, data gathering
├── testing/             # Unit tests, E2E, QA
└── web-development/     # React, Next.js, Vue, APIs
```

Don't see a category that fits? The Vault Master creates new ones automatically.

---

## Security

Every skill is scanned before it enters your vault. The Vault Master checks for:

- Dangerous commands (`rm -rf`, pipe-to-shell execution)
- Credential theft (reading SSH keys, AWS tokens, API keys)
- Data exfiltration (sending your files to external servers)
- Obfuscated code (hidden payloads in base64 or hex)
- Overly broad permissions
- Prompt injection attempts

| Rating | What it means |
|--------|--------------|
| **SAFE** | Clean — no risky operations detected |
| **CAUTION** | Some risk — review the findings before using |
| **DANGEROUS** | Red flag — you'll be warned before it's saved |

Full methodology in [`security-rubric.md`](security-rubric.md).

---

## Example Workflow

```
You:    /vault-add https://github.com/anthropics/skills/tree/main/skill-creator
Vault:  Analyzing skill... Rating: SAFE
        Saved to: categories/productivity/skill-creator.md
        Added to catalog.

You:    /vault-recommend I'm building a Next.js e-commerce app
Vault:  From your vault, I recommend:
        - shadcn-ui (design-ui) [SAFE] — UI components
        - playwright-cli (testing) [CAUTION] — E2E testing
        - vercel-deploy (devops-deploy) [SAFE] — Deployment

You:    /vault-discover SEO optimization
Vault:  Found 3 skills on skills.sh:
        - seo-audit [SAFE] — Technical SEO analysis
        - meta-tags-generator [SAFE] — Auto meta tags
        Add any of these? (y/n)
```

---

## Contributing

1. Fork this repo
2. Add skills with `/vault-add` or create entries manually in `categories/` using the template at `templates/skill-entry.md`
3. Submit a PR

---

## Built by

[Todo de IA](https://todoia.com) by [@soyenriquerocha](https://instagram.com/soyenriquerocha) — Building tools for the AI community.

## License

MIT
