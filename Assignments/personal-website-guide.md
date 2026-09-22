---
---

# Building Your Personal Website with VS Code + GitHub Pages

This guide walks you through creating a personal website hosted for free on GitHub Pages. You'll build it with VS Code and GitHub Copilot's help, and manage it with GitHub Desktop. By the end, you'll have:

- A homepage with an **About** section (and a photo)
- A link to your **resume/CV**
- A **Portfolio** page where you'll post assignments all semester — and eventually your final project

You can keep editing this site after class ends, so treat it like a real home base, not just an assignment.

---

## Before you start: one important decision

GitHub Pages treats one specific repository name as special: **`your-username.github.io`**. A repo with that *exact* name (using your real GitHub username) becomes your main personal site at the clean URL `https://your-username.github.io` — no extra folder in the address.

Any other repo name (like "Home") can still be turned into a website, but it publishes to a sub-address like `https://your-username.github.io/Home/`, and a few settings need to match that extra folder path.

**Recommendation:** Name the repository `your-username.github.io` (all lowercase, replacing "your-username" with your actual GitHub username). It's simpler, it's the "correct" personal site address, and it avoids a class of bugs where links and images work locally but break once published.

> If you've already created a repo called "Home," that's fine too — just let me know so we can adjust the settings that depend on the folder name (mainly image and link paths).

---

## Step 1: Create the repository on GitHub

1. Log into GitHub in your browser.
2. Click the **+** icon (top right) → **New repository**.
3. Name it `your-username.github.io` (swap in your real username).
4. Set it to **Public**. This isn't optional on a free GitHub account — Pages will only publish a site from a public repository unless you're on a paid plan. Don't worry: "public" means people can see your website's code, not anything private about your account.
5. Check **Add a README file**. This creates a starter `README.md` in the repo automatically, which just means the repo won't be empty when you clone it — GitHub shows this file's contents on the repo's main page, but it has no effect on your actual website.
6. Click **Create repository**.

### Turn on GitHub Pages

1. On your new repo's page, go to **Settings** (top tab) → **Pages** (left sidebar, under "Code and automation").
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Under **Branch**, select `main` and folder `/ (root)`, then **Save**.
4. GitHub will take a minute to build and give you a live URL (it'll say "Your site is live at https://your-username.github.io"). It won't have real content yet — that's fine, you're just confirming Pages is switched on before you start building.

### Set the repo's URL (the gear icon)

1. Go back to your repo's main page (click the repo name, or **Code** tab).
2. On the right-hand side, find the **About** section and click the small **gear icon** ⚙️.
3. In the panel that opens, check the box **Use your GitHub Pages website**. This auto-fills the Website field with your live Pages URL, so anyone visiting your repo can click straight through to your actual site.
4. Click **Save changes**.

> **Already created your repo?** If you made a repository before reading this guide — even with a different name, or without the README — that's okay. You don't need to delete it and start over. Just make sure it's **Public** (Settings → General → scroll to "Danger Zone" → "Change visibility" if it's currently Private), then continue with Steps 2–4 below using that existing repo. When you get to Step 6, you'll build the folder/file structure inside it and **overwrite** whatever `index.html` (or `README.md`) is already there — that's expected.

---

## Step 2: Set up your local folder (avoid Google Drive / OneDrive syncing)

We want this folder to live somewhere that isn't auto-synced to cloud storage (Google Drive, OneDrive, iCloud Drive), since sync conflicts can corrupt Git repositories.

**Both Mac and PC:**
1. Open **Documents**.
2. Create a new folder named `GitHub` (this will hold all your class/personal repositories going forward).

> **Mac users:** if iCloud Drive is set to sync your whole Desktop and Documents folder, either turn that off, or create the `GitHub` folder somewhere else not covered by sync (e.g., directly in your user folder, or in a location you know isn't synced).

---

## Step 3: Clone the repo with GitHub Desktop

1. Open **GitHub Desktop** and sign in with your GitHub account if you haven't already.
2. Go to **File → Clone Repository**.
3. Select your `your-username.github.io` repo from the list.
4. For **Local Path**, choose the `Documents/GitHub` folder you just made.
5. Click **Clone**.

You now have a local copy of your website's folder that's connected to GitHub.

---

## Step 4: Open the folder in VS Code

1. Open **VS Code**.
2. **File → Open Folder** → select `Documents/GitHub/your-username.github.io`.
3. If prompted, install the **GitHub Copilot** and **GitHub Copilot Chat** extensions (Extensions icon in the left sidebar, search "Copilot").

### If Copilot Chat isn't working

Some of you may have accidentally clicked "disable" on an AI/Copilot prompt during setup. If Copilot Chat doesn't appear (there should be a chat icon in the left sidebar, or an icon in the top-right of the editor), check:

1. **Extensions** (left sidebar) → search "Copilot" → make sure both **GitHub Copilot** and **GitHub Copilot Chat** show a blue **Enable** button turned on (not "Disable" grayed out — if it says "Disable," it's already on; if it says "Enable," click it).
2. Click the **Accounts** icon (bottom left, person-shaped icon) → make sure you're signed into GitHub and that it shows Copilot as active.
3. If you still don't see it, try **Command Palette** (`Cmd+Shift+P` on Mac / `Ctrl+Shift+P` on PC) → type "Copilot" → look for an option like "GitHub Copilot: Enable" and select it.

### Recommended extensions

While you're in the Extensions panel, install these — they'll make writing HTML/CSS much easier:

- **HTML Tag Wrap** — lets you select text and quickly wrap it in an HTML tag (e.g., select a word, trigger the shortcut, choose `<strong>`) instead of typing opening and closing tags by hand.
- **Rainbow CSV** — colors CSV columns and improves readability of comma/tab-separated files. Handy if you ever import data into your portfolio.

### Turn on word wrap (so lines don't run off-screen)

This is a built-in VS Code setting, not an extension. Long lines of HTML/CSS will otherwise scroll horizontally instead of wrapping visibly on screen. To fix it:

- Press **Alt+Z** (PC) or **Option+Z** (Mac) to toggle word wrap on/off in the current file, **or**
- Make it permanent: **Code/File → Preferences → Settings** → search "word wrap" → set **Editor: Word Wrap** to `on`.

---

## Step 5: Gather your materials

Before building, collect these files and save them somewhere handy (like your Desktop, to drag into VS Code later):

- A **photo** of yourself (or an image you're comfortable using publicly) — JPG or PNG
- Your **resume or CV** as a PDF
- A few sentences about yourself: your major, interests, what this course is, anything you want visitors to know

---

## Step 6: Build the site structure

In VS Code, create this folder/file structure. You can do this by hand (right-click in the Explorer panel → New File / New Folder), or ask Copilot Chat to scaffold it for you (see prompt below).

```
your-username.github.io/
├── index.html          ← homepage (About page)
├── portfolio.html       ← lists your assignments
├── style.css            ← shared styling
├── assets/
│   ├── images/
│   │   └── profile.jpg      (your photo)
│   ├── resume.pdf
│   └── portfolio/           (assignment files go here)
```

We're using plain HTML/CSS rather than Jekyll templates — this keeps everything visible and editable, and works identically on GitHub Pages with no extra configuration.

### Prompting Copilot Chat to build the first draft

Open **Copilot Chat** (icon in the sidebar) and try a prompt like this, filling in your own info:

> "Help me build a simple personal website with three files: index.html, portfolio.html, and style.css. index.html should have a short bio about me: [paste your 3–5 sentences]. Include a placeholder for a profile photo at assets/images/profile.jpg, and a link to my resume at assets/resume.pdf. Include a nav bar linking to Portfolio. portfolio.html should say this is where I'll post class assignments, with an empty list I can add links to later. Use a clean, modern design in style.css — nothing flashy yet, I want to customize it myself."

Then drag your photo into `assets/images/` and rename it `profile.jpg` (or update the filename in the HTML to match). Do the same with your resume PDF into `assets/`, named `resume.pdf`.

---

## Step 7: Preview your site locally

Install the **Live Server** extension in VS Code (search in Extensions), then right-click `index.html` → **Open with Live Server**. This opens your site in a browser and auto-refreshes as you edit — much faster than pushing to GitHub every time you want to check something.

---

## Step 8: Play with the design

This is your site — make it feel like you. Some starting points to try with Copilot:

- "Change the color scheme to something inspired by [a color/theme you like]"
- "Make the fonts more modern — suggest a Google Fonts pairing for headings and body text"
- "Add a subtle hover effect to the navigation links"
- "Make the layout responsive so it looks good on a phone"

Don't be afraid to ask Copilot *why* it wrote something a certain way — that's part of learning to read and adjust CSS yourself.

---

## Step 9: Push your changes live

1. Open **GitHub Desktop**. It will show all the files you've changed.
2. Write a short summary in the **Summary** box (e.g., "Add homepage and portfolio page").
3. Click **Commit to main**.
4. Click **Push origin** (top right).

## Step 10: Turn on GitHub Pages

1. On GitHub.com, go to your repo → **Settings** → **Pages** (left sidebar).
2. Under **Source**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. Click **Save**.
4. After a minute or two, your site will be live at `https://your-username.github.io`.

---

## Ongoing workflow (for the rest of the semester)

Every time you want to add an assignment to your Portfolio:

1. **Pull first** in GitHub Desktop (in case you edited from another computer) — click **Fetch origin**, then **Pull origin** if changes are shown.
2. Add your new assignment file(s) into `assets/portfolio/`.
3. Add a link to it from `portfolio.html`.
4. Preview with Live Server to check it looks right.
5. In GitHub Desktop: **Commit** with a short message → **Push origin**.
6. Give it a minute, then check `https://your-username.github.io/portfolio.html` to confirm it's live.

---

## Quick troubleshooting

| Problem | Likely cause |
|---|---|
| Site shows 404 | Pages isn't enabled yet, or it's still deploying (wait 1–2 min) |
| Image doesn't show | Check the file path/name matches exactly, including capitalization |
| Changes not showing on live site | Did you Commit *and* Push in GitHub Desktop? |
| "Nothing to commit" in GitHub Desktop | You may have forgotten to save the file in VS Code first |
