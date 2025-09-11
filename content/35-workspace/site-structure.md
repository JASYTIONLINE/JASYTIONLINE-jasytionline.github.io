---
title: Master Plan – Repo & Site Structure (v2)
description: Visual map + explicit, step‑by‑step instructions for publishing and activating sections. Cold-reader friendly.
date: 2025-09-11
role: plan
classification: internal
id: site-structure-master-v2
shortcode: plan-structure-v2
aliases:
  - site-structure
  - repo-tree
  - publishing-guide
version: "2.0"
---

# Master Plan – Repo & Site Structure (v2)

**Site Root (GitHub Pages):** `repo-root/`  
**Obsidian Root (KB):** `repo-root/content/`

> This single page explains (1) what the folder tree is, (2) what you **must** set up for publishing, and (3) **exactly** how to publish and later activate more sections. No leaps required.

## Visual Tree (Authoritative)

```text
repo-root/                         <-- Site Root (public GH Pages root)
├─ README.md
├─ .gitignore                      (ignore .obsidian/, large locals, etc.)
├─ LICENSE
├─ SECURITY.md
├─ CONTRIBUTING.md
├─ .github/
│  ├─ ISSUE_TEMPLATE.md
│  ├─ PULL_REQUEST_TEMPLATE.md
│  └─ workflows/ci.yml
├─ assets/                         <-- Shared static assets (public)
│  ├─ style.css
│  ├─ img/
│  │  └─ (images...)
│  └─ js/
│     └─ (scripts if needed)
└─ content/                        <-- Obsidian Root (G-3 root; site section hub)
   ├─ index.md                     (MASTER: YAML active; KB nav + optional HTML)
   ├─ index.html                   (MIRROR: YAML commented; links ../assets/style.css)
   ├─ 33-deliverables/            <-- G-33 (Public-facing deliverables)
   │  ├─ index.md                 (KB index)
   │  ├─ index.html               (Public section landing)
   │  └─ p02/
   │     ├─ cr-wk5p2-your-professional-project-repository.md
   │     ├─ readme-p02.md
   │     └─ submission/
   │        ├─ live-site-url.txt
   │        └─ repo-url.txt
   ├─ 35-workspace/               <-- G-35 (Drafts & Builds; planning artifacts)
   │  ├─ index.md
   │  ├─ index.html
   │  ├─ plans/
   │  │  └─ site-structure.md     (v1) / site-structure_v2.md (THIS FILE)
   │  ├─ drafts/
   │  └─ builds/
   ├─ 37-knowledge/
   │  ├─ index.md
   │  ├─ index.html
   │  ├─ references.md
   │  └─ glossary.md
   ├─ 38-supporting-docs/
   │  ├─ index.md
   │  ├─ index.html
   │  ├─ decisions/
   │  │  └─ ADR-0001-init.md
   │  └─ evidence/
   └─ 39-mwr/
      ├─ index.md
      ├─ index.html
      └─ learning-log.md

# Local-only (do NOT commit)
#   .obsidian/  ← keep at local workspace root; add to .gitignore
```

---

## MUST‑HAVE SETUP (Do this before publishing)

1) **Shared CSS exists**  
   - File: `repo-root/assets/style.css`  
   - Purpose: One stylesheet for all public HTML pages.  
   - If missing: create `assets/` at repo root and add `style.css`.

2) **Public entry page exists**  
   - File: `repo-root/content/index.html`  
   - It must include this line in the `<head>` (exact path):  
     ```html
     <link rel="stylesheet" href="../assets/style.css">
     ```

3) **Only G‑33 is active (initially)**  
   - In `content/index.html`, the G‑33 link is visible.  
   - G‑35 / G‑37 / G‑38 / G‑39 links are present but **wrapped in `<!-- ... -->` comments**.

---

## HOW TO PUBLISH FROM THE MASTER (`content/index.md`) — Step by Step

**Goal:** Convert your Markdown master into the public HTML homepage under `content/`.

1) **Open master**  
   - Open `repo-root/content/index.md` in VS Code.

2) **Comment the YAML for HTML**  
   - Surround the YAML header with HTML comments so browsers ignore it:  
     ```html
     <!--
     ---
     title: ...
     ... (rest of YAML)
     ---
     -->
     ```

3) **Ensure the HTML block exists**  
   - Your file should contain an HTML section with a title and links. If not, paste your approved HTML homepage markup (kept in this repo).

4) **Save As HTML**  
   - File → Save As… → `index.html` (same `content/` folder).  
   - Confirm it **overwrites** the old `index.html` if prompted.

5) **Verify the CSS link**  
   - In `content/index.html`, confirm the stylesheet link is:  
     ```html
     <link rel="stylesheet" href="../assets/style.css">
     ```

6) **Commit and push (GitHub Desktop)**  
   - Commit message (example):  
     `feat: publish content/index.html from master index.md (G-33 active)`  
   - Click **Push origin**.

7) **Open the site**  
   - Visit `https://<your-username>.github.io/content/` (or your configured path).  
   - Allow up to 10 minutes for GitHub Pages to refresh.

**Quick Test:** You should see the styled homepage and a working link to **G‑33 Deliverables**.

---

## HOW TO ACTIVATE A NEW SECTION (Example: G‑35)

**Goal:** Turn on the G‑35 link in the public homepage when the folder is ready.

A) **Confirm the folder is ready**  
   - `repo-root/content/35-workspace/index.md` exists (KB).  
   - Optional: `repo-root/content/35-workspace/index.html` exists (public landing).

B) **Uncomment the link in the homepage**  
   - Open `repo-root/content/index.html`.  
   - Find the commented G‑35 block:
     ```html
     <!--
     <p>
       <a href="35-workspace/index.md"
          title="Navigate to the Workspace folder (G-35)">
         G-35 Workspace (Drafts & Builds)
       </a>
     </p>
     -->
     ```
   - Remove the `<!--` and `-->` so it becomes:
     ```html
     <p>
       <a href="35-workspace/index.md"
          title="Navigate to the Workspace folder (G-35)">
         G-35 Workspace (Drafts & Builds)
       </a>
     </p>
     ```

C) **Commit and push**  
   - Commit message (example):  
     `feat: activate G-35 link on G-3 homepage`  
   - Push.

D) **Verify**  
   - Open the public homepage and click **G‑35**.  
   - It should open the KB page (`index.md` rendered on GitHub) or your public landing (`index.html`) if present.

**Repeat** for G‑37, G‑38, G‑39 using the same pattern.

---

## KB vs Public – Sanity Checks

- **KB pages (`.md`)** are for Obsidian and GitHub repo view. They contain **YAML** and prose.  
- **Public pages (`.html`)** are what GitHub Pages serves to visitors. They **link the shared CSS** and show only what you’ve uncommented.

**If a link looks unstyled:** check that the target is an `.html` page with the proper `<link rel="stylesheet" href="../assets/style.css">` (or `../../assets/style.css` for deeper folders).

---

## Maintenance Tips

- Keep `<nav>` blocks identical across section `index.html` files for a consistent UX.  
- Use small, purposeful commits with descriptive messages matching rubric language.  
- Avoid committing `.obsidian/` and large binaries; keep backups outside the repo.
