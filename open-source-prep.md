# Public Release Prep Checklist

Use this file as a prompt context for an AI agent to prepare a finished project for public release as a portfolio piece. The project is not looking for contributors — it just needs to be clean, presentable, and safe to make public.

---

## Agent Instructions

Work through each section below in order. For each item, check the codebase and either confirm it passes or fix it. Report what was found and what was changed.

---

## 1. Secrets & Credentials Audit

- [ ] No hardcoded API keys, passwords, or tokens in source files
- [ ] No `.env` files committed (only `.env.example` with placeholder values)
- [ ] `.gitignore` covers `.env*`, `*.pem`, `*.key`
- [ ] No internal URLs, private IPs, or personal hostnames in source

## 2. Personal Information

- [ ] No real email addresses in source or docs
- [ ] No phone numbers outside of clearly fake test fixtures
- [ ] No personal names hardcoded except in LICENSE copyright line

## 3. Git History

- [ ] No `Co-Authored-By` lines in commit messages (strips AI co-author attribution)
- [ ] No accidentally committed secrets in history

To strip Co-Authored-By from all commits and force push:
```bash
FILTER_BRANCH_SQUELCH_WARNING=1 git filter-branch --msg-filter '
  sed "/^Co-Authored-By:/Id" | sed "/^[[:space:]]*$/d"
' -- --all
git push --force origin main
```

## 4. README Quality

- [ ] One-line description at the top
- [ ] Features list
- [ ] Setup / installation instructions
- [ ] Screenshots or demo GIF if it is a UI project
- [ ] No em dashes (—) or en dashes (–) — replace with regular hyphens (-)
- [ ] No broken links
- [ ] Tech stack mentioned

## 5. Required Files

- [ ] `README.md`
- [ ] `LICENSE` - MIT is standard for portfolio work
  - Copyright year and name are correct

## 6. .gitignore Completeness

**Python:** `__pycache__/`, `*.pyc`, `venv/`, `.venv/`
**Node/JS:** `node_modules/`, `dist/`, `.next/`
**General:** `.env*`, `*.pem`, `*.key`, `.DS_Store`, `Thumbs.db`, `.vscode/`, `.idea/`

## 7. Code Cleanliness

- [ ] No debug `print()` / `console.log()` statements left in production paths
- [ ] No large commented-out blocks of old code
- [ ] No TODO/FIXME comments that expose unfinished work

## 8. GitHub Repository Settings (manual)

After pushing, set these on the GitHub repo page:

- **Description:** One sentence, what it does
- **Topics:** 5-8 relevant tags (language, framework, category)
- **Website:** Live demo URL if deployed, otherwise leave blank
- **Releases:** Enable and tag a v1.0 release
