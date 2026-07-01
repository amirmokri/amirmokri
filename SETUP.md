# 🚀 Profile README — Setup Guide

You have 3 files:

```
profile-readme/
├── README.md                       ← your profile page
├── SETUP.md                        ← this guide
└── .github/
    └── workflows/
        ├── snake.yml               ← generates the 🐍 animation
        └── 3d-contrib.yml          ← generates the 3D contribution graph
```

---

## Step 1 — Create the special repo

Create a **new public repo named EXACTLY your GitHub username**.
Example: if you are `github.com/jane`, the repo must be named `jane`.

> GitHub only renders a profile README from this specifically-named repo.
> Tick "Add a README" — you'll overwrite it in the next step.

## Step 2 — Add the files

Copy `README.md` and the whole `.github/` folder into that repo (keep the
folder structure). Commit to the `main` branch.

## Step 3 — Fill in your details

Open `README.md` and find-and-replace these tokens:

| Token | Replace with |
|-------|--------------|
| `YOUR_USERNAME` | your GitHub username (exact case) — appears many times |
| `YOUR_NAME` | your display name |
| `YOUR_ROLE` | e.g. "Full-Stack Developer" |
| `<<YOUR_WEBSITE_URL>>` | your site (or delete that badge) |
| `<<YOUR_X_HANDLE>>` | your X/Twitter handle |
| `<<YOUR_LINKEDIN>>` | your LinkedIn slug |
| `<<YOUR_EMAIL>>` | your email |
| `<<REPO_1>>`, `<<REPO_2>>` | repos to feature |
| all `<<...>>` in About Me | your own words |

Then **trim the Tech Stack badges** down to what you actually use.

## Step 4 — Turn on Actions & run them once

1. In the repo, go to **Settings → Actions → General** →
   set **Workflow permissions** to **"Read and write permissions"** → Save.
   *(Without this, the workflows can't push the generated files.)*
2. Go to the **Actions** tab. If prompted, click "I understand, enable workflows".
3. Run each workflow manually the first time:
   - **Generate 3D Contribution Graph** → *Run workflow*
   - **Generate Snake Animation** → *Run workflow*

After they finish (green check):
- The 3D graph appears at `profile-3d-contrib/profile-night-rainbow.svg` on `main`.
- The snake SVGs appear on a new `output` branch.

Refresh your profile — everything renders. From now on they auto-update on a schedule.

---

## Troubleshooting

- **3D graph / snake shows a broken image** → the workflow hasn't run yet, or
  Step 4.1 (write permissions) wasn't done. Run the workflow and re-check.
- **Stats card shows 0 / private contributions missing** → normal; `count_private=true`
  only counts what the card service can see. Optional: deploy your own instance of
  github-readme-stats to include all private commits (see that project's README).
- **Snake URL 404** → confirm the `output` branch exists after the snake workflow ran,
  and that `YOUR_USERNAME` matches exactly in the raw URLs.
- **Want a different 3D style** → the action also generates `profile-night-green.svg`,
  `profile-season-animate.svg`, `profile-gitblock.svg`, etc. Swap the filename in README.md.

---

## What makes this better than a typical profile

- Animated wave banner + typing tagline (motion the moment someone lands)
- Snake contribution animation 🐍 (dark/light aware)
- 3D contribution graph (Tokyo Night rainbow)
- Trophy case + activity graph + streak + top languages
- Themed, consistent Tokyo Night palette across *every* widget
- Auto-updating via GitHub Actions — it stays fresh with zero effort

**The one thing this can't do for you:** be backed by a real project.
Widgets are the frame; a genuinely useful pinned repo is the picture.
That's what turns a pretty profile into followers.
