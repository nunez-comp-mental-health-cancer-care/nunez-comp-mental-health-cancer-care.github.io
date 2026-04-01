# Website Management Setup Guide (Non‑Technical)

This guide is for a lab member with **no tech background** who needs to update the lab website content and publish changes.

This website is built with **Hugo v0.88.1** (an older version). Use that version unless a technical teammate tells you otherwise.

---

## What you will install (one time)

1. **GitHub Desktop** (to download the website project and upload your changes)
2. **Visual Studio Code (VS Code)** (to edit the website files)
3. **Hugo 0.88.1** (to preview/build the website on your computer)

Optional (only if you see a specific error about “go” later):
4. **Go (programming tool)** — Hugo needs it to download the website theme modules the first time.

---

## Big picture (in plain words)

- The website “source files” live in a folder on GitHub (online).
- You download that folder to your computer using **GitHub Desktop**. This is called **cloning**.
- You edit the text/images in the `content/` folder using **VS Code**.
- You run **Hugo** to preview the site on your computer.
- When it looks good, you **commit** and **push** your changes back to GitHub.
- GitHub Pages will then show the updated website.

---

## Step 0 — Get access to the GitHub repo (do this first)

1. Create a GitHub account (if you don’t have one):
   - Go to GitHub in your browser.
   - Click **Sign up** and follow the steps.
2. Ask a teammate to add your GitHub account to this repo:
   - Repo name: `nunez-comp-mental-health-cancer-care.github.io`
3. Watch your email for an invitation from GitHub, then click **Accept invitation**.

If you can’t access the repo page after this, ask a teammate to confirm your access.

---

## Step 1 — Install GitHub Desktop

GitHub Desktop is the easiest way to download the project and upload your updates.

Official download page:
- https://desktop.github.com/

### Windows installation

1. Open your web browser and search: **GitHub Desktop download**.
2. Open the official GitHub Desktop page and click **Download for Windows**.
3. Open the downloaded installer (usually in **Downloads**).
4. Follow the prompts:
   - If Windows asks “Do you want to allow this app to make changes?”, click **Yes**.
5. After it installs, GitHub Desktop should open automatically.

### macOS installation

1. Open your web browser and search: **GitHub Desktop download**.
2. Open the official GitHub Desktop page and click **Download for macOS**.
3. Open the downloaded `.zip` file (usually in **Downloads**).
4. Drag **GitHub Desktop** into your **Applications** folder.
5. Open **Applications** → **GitHub Desktop**.
   - If macOS says it’s from the internet, click **Open**.

### Sign in and basic settings (Windows + macOS)

1. In GitHub Desktop, click **Sign in to GitHub.com**.
2. Complete the login in your browser, then return to GitHub Desktop.
3. When asked about your name/email:
   - Use your real name.
   - Email can be your GitHub email or your work email (either is fine).
4. (Recommended) Set VS Code as your editor:
   - GitHub Desktop → **Settings** (or **Preferences** on Mac)
   - **Integrations** → **External editor** → choose **Visual Studio Code**

---

## Step 2 — Install Visual Studio Code (VS Code)

VS Code is a free editor that is beginner-friendly and works on Windows/Mac.

Official download page:
- https://code.visualstudio.com/

### Windows installation

1. Search in your browser: **Visual Studio Code download**.
2. Open the official VS Code website and click **Download for Windows**.
3. Open the installer from your **Downloads** folder.
4. During installation:
   - Keep the default options unless you’re sure.
   - If you see an option like “Add to PATH” or “Register Code as an editor”, it’s okay to enable it.
5. Finish installation and open **Visual Studio Code**.

### macOS installation

1. Search in your browser: **Visual Studio Code download**.
2. Open the official VS Code website and click **Download for macOS**.
3. Open the downloaded `.zip` file (or `.dmg` depending on the version).
4. Drag **Visual Studio Code** into **Applications**.
5. Open **Applications** → **Visual Studio Code**.

### Recommended VS Code first-time settings (quick)

These make editing easier:

1. Turn on autosave:
   - VS Code menu → **File** → **Auto Save**
2. Make the left file list visible:
   - VS Code menu → **View** → **Explorer**
3. If VS Code asks “Do you trust the authors of the files in this folder?”:
   - For this lab repo, choose **Trust** (if it’s the correct repo).

---

## Step 3 — Install Hugo v0.88.1 (important)

This repo is built for **Hugo 0.88.1**.

Official Hugo v0.88.1 download page:
- https://github.com/gohugoio/hugo/releases/tag/v0.88.1

### Important note: “extended” vs “regular”

Some Hugo themes require the **extended** version (common when a theme uses advanced styling).
If you’re unsure, **download Hugo Extended 0.88.1**.

### 3A — Download Hugo 0.88.1

1. Open your browser and go to the Hugo v0.88.1 release page on GitHub.
2. Scroll until you find a section called **Assets**.
3. Download the right file for your computer:

- **Windows (most people):**
  - Choose a file ending with `Windows-64bit.zip`
  - Prefer one that says `extended` in the name
  - Example: `hugo_extended_0.88.1_Windows-64bit.zip`
- **Mac (Apple Silicon M1/M2/M3 or Intel):**
  - Prefer a `macOS-universal.tar.gz` asset if available
  - Prefer one that says `extended` in the name
  - Example: `hugo_extended_0.88.1_macOS-universal.tar.gz`

When the download finishes, you will have a `.zip` (Windows) or `.tar.gz` (Mac) file.

### 3B — Install Hugo on Windows (detailed)

Goal: end up with `hugo.exe` in a permanent folder and make Windows able to find it.

1. Create a folder for Hugo:
   - Open **File Explorer**
   - Go to `C:\`
   - Create a new folder named `Hugo`
   - Inside `C:\Hugo`, create another folder named `bin`
   - Final folder should be: `C:\Hugo\bin`
2. Unzip Hugo:
   - Find the downloaded Hugo `.zip` file (usually in **Downloads**)
   - Right-click → **Extract All…**
   - After extracting, find `hugo.exe`
3. Move `hugo.exe` into `C:\Hugo\bin`
4. Add `C:\Hugo\bin` to your PATH:
   - Press the **Windows key** and search: `environment variables`
   - Click **Edit the system environment variables**
   - Click **Environment Variables…**
   - Under **User variables** (top section), find **Path** and click **Edit…**
   - Click **New**
   - Paste: `C:\Hugo\bin`
   - Click **OK** → **OK** → **OK**
5. Close and re-open any terminals/VS Code windows (PATH changes usually require restarting apps).

### 3C — Install Hugo on macOS (detailed)

Goal: put the `hugo` file in a folder that your Mac can run from Terminal.

1. Create a “bin” folder in your home folder (safe and simple):
   - Open **Terminal**
   - Copy/paste and press Enter:
     - `mkdir -p ~/bin`
2. Extract the downloaded Hugo file:
   - In Finder, open **Downloads**
   - Double-click the `.tar.gz` file to extract it
   - You should get a file named `hugo`
3. Move `hugo` into `~/bin`:
   - In Terminal, run (adjust the path if needed):
     - `mv ~/Downloads/hugo ~/bin/hugo`
4. Make it executable:
   - `chmod +x ~/bin/hugo`
5. Add `~/bin` to your PATH (zsh is the default on modern macOS):
   - `nano ~/.zshrc`
   - Add this line at the end:
     - `export PATH="$HOME/bin:$PATH"`
   - Save and exit:
     - Press `Ctrl+O`, then Enter to save
     - Press `Ctrl+X` to exit
   - Reload your terminal settings:
     - `source ~/.zshrc`

If macOS blocks Hugo the first time (Gatekeeper):
1. Try running `hugo version` in Terminal once.
2. If macOS says it can’t be opened, go to:
   - **System Settings** → **Privacy & Security**
   - Look for a message about `hugo` being blocked and click **Open Anyway**

### 3D — Verify Hugo is installed (Windows + macOS)

1. Open Terminal:
   - Windows: open **Command Prompt** or **PowerShell**
   - Mac: open **Terminal**
2. Run:
   - `hugo version`
3. You should see something that includes `v0.88.1`.

If you get “command not found” (Mac) or “not recognized” (Windows), the PATH step didn’t work yet.

---

## Step 4 — Download the website project to your computer (clone)

We recommend cloning with GitHub Desktop (much easier than the command line).

1. Open **GitHub Desktop**
2. Click **File** → **Clone repository…**
3. Click the **URL** tab (or choose from the list if it appears)
4. Paste the repo URL (a teammate can send it to you)
5. Choose a **Local path** (where it will live on your computer), for example:
   - Windows: `Documents\GitHub\`
   - Mac: `Documents/GitHub/`
6. Click **Clone**

After cloning, you now have a folder on your computer containing the website source files.

---

## Step 5 — Open the project in VS Code

Option A (recommended):
1. In GitHub Desktop, go to **Repository** → **Open in Visual Studio Code**

Option B:
1. Open VS Code
2. Click **File** → **Open Folder…**
3. Select the cloned repo folder

---

## Step 6 — Edit the website content (the safe part)

Only edit files inside:
- `content/`

Start by reading:
- `CONTENT_GUIDE.md` (this repo’s content editing guide)

Tips:
- Don’t edit the `docs/` folder by hand. `docs/` is the generated website output.
- If you’re editing a `.md` file (Markdown), it’s normal to see lots of text plus small symbols like `#` and `-`.
- In VS Code you can preview Markdown:
  - Right-click the file tab → **Open Preview**

---

## Step 7 — Preview the website on your computer

1. In VS Code, open the terminal:
   - VS Code menu → **Terminal** → **New Terminal**
2. Make sure you are in the website folder:
   - If you’re not sure, close VS Code and open the repo again from GitHub Desktop (Step 5).
3. Run:
   - `hugo server -D`
4. In your browser, open:
   - `http://localhost:1313`
5. Keep Hugo running while you edit:
   - When you save a file, refresh the browser to see changes.
6. To stop Hugo:
   - Click the terminal and press `Ctrl+C`

If you see “port 1313 already in use”, run:
- `hugo server -D -p 1314`
Then open `http://localhost:1314`.

---

## Step 8 — Build the website output (creates `docs/`)

When you’re ready to publish:

1. In VS Code terminal (in the repo folder), run:
   - `hugo --gc --minify`
2. This generates the final website files into:
   - `docs/`

It is normal for many files to change in `docs/` after a build.

---

## Step 9 — Publish your changes (upload to GitHub)

1. Open **GitHub Desktop**
2. You will see a list of changed files
3. Write a short summary message (bottom left), for example:
   - `Update lab member bio`
4. Click **Commit to main**
5. Click **Push origin**

After pushing, wait a minute or two and check the live website.

---

## Troubleshooting (common problems)

### “hugo: command not found” (Mac) / “not recognized” (Windows)

- This usually means Hugo isn’t on your PATH yet.
- Re-check Step 3 (PATH steps), then fully close and re-open:
  - Terminal
  - VS Code
  - GitHub Desktop (sometimes)

### Hugo complains about modules, Git, or “go”

This site uses Hugo “modules” (it downloads the theme).

If you see an error mentioning:
- `go: not found`
- `failed to download modules`
- `git: not found`

Try these fixes:
1. Confirm you have internet access (the first build needs downloads).
2. Confirm GitHub Desktop is installed (it usually installs Git tools automatically).
3. If you specifically see **go** errors, install **Go**:
   - Official download page: https://go.dev/dl/
   - Install the recommended version for your computer
   - Restart VS Code and try `hugo server -D` again

If it still fails, copy/paste the exact error message to a technical teammate (or to ChatGPT) — the wording matters.

### The website looks wrong or missing styling

- Make sure you installed **Hugo Extended v0.88.1**
- Run `hugo version` and confirm it says `v0.88.1`
- Re-run `hugo --gc --minify`

---

## Quick checklist (after everything is set up)

Each time you want to update the website:

1. Open GitHub Desktop → open the repo
2. Open in VS Code
3. Edit files in `content/`
4. Preview: `hugo server -D` → check `http://localhost:1313`
5. Build: `hugo --gc --minify` (creates/updates `docs/`)
6. In GitHub Desktop: Commit → Push
