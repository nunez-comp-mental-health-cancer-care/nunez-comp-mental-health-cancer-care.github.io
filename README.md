[nunez-comp-mental-health-cancer-care.github.io](https://nunez-comp-mental-health-cancer-care.github.io/)


# instructions on editing the website content for members who code
- This lab website is built on an old theme based on hugo 0.88. 
- To edit the site, you will need to install [hugo 0.88](https://github.com/gohugoio/hugo/releases/tag/v0.88.1).

- Read `content_guide.md` for instructions on how to edit the website content.
- edit the `content/` folder to change the website content. You can ignore all other files.
- run in command line `hugo --gc --minify` to build the website locally. The generated website will be in the public/ folder.
- run `hugo server -D` to preview the website locally.
- commit and push changes to the main branch to update the website online.


# Beginner's Guide to Editing the Lab Website

if you want to do it really quickly, just read `content_guide.md`, and edit files in`content/`. And ask a team member to generate the website file real quick(takes 20 seconds if they know how to do it)

# Really detailed guide to do it yourself from scratch

This lab website is built using Hugo (a tool that helps create websites). Don't worry if you've never heard of Hugo or coding before—this guide will walk you through everything step-by-step.

---

## Step 1: Download Hugo

Hugo is a software tool you need to download and install on your computer first.

### What is Hugo?
Hugo is a program that takes your content (text, images, etc.) and turns it into a website. Think of it as a translator that converts your files into a proper website format.

### How to Download and Install Hugo (version 0.88)

1. **Open your web browser** and go to: https://github.com/gohugoio/hugo/releases/tag/v0.88.1

2. **Find your operating system** and download the correct file:
   - **Windows users**: Look for a file ending in `.zip` (like `hugo_0.88.1_Windows-64bit.zip`)
   - **Mac users**: Look for a file ending in `.tar.gz` (like `hugo_0.88.1_macOS-universal.tar.gz`)
   - **Linux users**: Look for the Linux version

3. **Extract/Unzip the file** once it downloads:
   - Right-click the downloaded file and choose "Extract All" or "Unzip"
   - Remember where you save it (like your Desktop or Documents folder)

4. **Make it easy to find**: Add Hugo to your computer's PATH

   **What is PATH?** PATH is a list of locations on your computer where it looks for programs. By adding Hugo to PATH, your computer knows where to find Hugo when you type commands in the terminal.

   **How to do it:**
   
   **For Windows:**
   - Right-click "This PC" or "My Computer" on your desktop or File Explorer
   - Click "Properties"
   - Click "Advanced system settings" on the left
   - Click "Environment Variables" at the bottom
   - Under "User variables", click "New"
   - Type `PATH` in the Variable name box
   - In the Variable value box, paste the full path where you extracted Hugo (example: `C:\Users\YourName\Desktop\Hugo`)
   - Click "OK" three times
   - Restart your computer

   **For Mac:**
   - Open Terminal
   - Type: `sudo nano ~/.zshrc` and press Enter
   - Add this line at the end: `export PATH="$PATH:/path/to/hugo"`
   - Replace `/path/to/hugo` with where you extracted Hugo
   - Press Ctrl+X, then Y, then Enter to save
   - Type: `source ~/.zshrc` and press Enter

   **For Linux:**
   - Open Terminal
   - Type: `sudo nano ~/.bashrc` and press Enter
   - Add this line at the end: `export PATH="$PATH:/path/to/hugo"`
   - Replace `/path/to/hugo` with where you extracted Hugo
   - Press Ctrl+X, then Y, then Enter to save
   - Type: `source ~/.bashrc` and press Enter

   **Don't understand this part?** That's totally okay! Ask your project manager or a colleague to help you with this step—it's a one-time setup thing.

### How to Check if Hugo is Installed Correctly

1. Open your **Command Prompt** (Windows) or **Terminal** (Mac/Linux):
   - Windows: Press `Windows key + R`, type `cmd`, press Enter
   - Mac: Press `Command + Space`, type `terminal`, press Enter
   - Linux: Open your terminal application

2. Type this command and press Enter:
   ```
   hugo version
   ```
   If it shows a version number, Hugo is installed correctly!

---

## Step 2: Understand GitHub

GitHub is a platform where your website files are stored online. It's like a cloud storage service (like Dropbox or Google Drive) but specifically designed for projects.

### What You Need to Do with GitHub

1. **Create a GitHub account** (if you don't have one):
   - Go to https://github.com
   - Click "Sign up"
   - Follow the instructions

2. **Access the lab website project**: Ask the team member who has access to the lab's website folder on GitHub to give you access. This folder contains all the files that make up your website.

3. **Download the project files to your computer**:
   - Go to the project page on GitHub
   - Click the green `Code` button
   - Click `Download ZIP`
   - Extract/unzip this folder somewhere on your computer (like your Documents folder)
   - Remember where you saved it!

---

## Step 3: Edit the Website Content

All the content (text, images, descriptions) is stored in the **`content/` folder**.

### How to Edit Content

1. **Open the `content/` folder** on your computer using any text editor:
   - you can use free programs like Visual Studio Code or Notepad++
   - or use any markdown editor online like https://markdownlivepreview.com/

2. **Read the `content_guide.md` file**: Before you edit anything, open and read the file called `content_guide.md`. It contains specific instructions for editing content for this website.

3. **Edit only the `content/` folder**: Only change files inside the `content/` folder. Ignore all other folders and files—they're for technical settings that you don't need to touch.

4. **Save your changes**: After editing, save your files normally (Ctrl+S or Command+S).

---

## Step 4: Preview Your Changes Locally

Before you update the website online, you can see what it looks like on your computer.

### How to Preview

1. **Open Command Prompt/Terminal** (see Step 1 for instructions)

2. **Navigate to your project folder**: Type this command and press Enter:
   ```
   cd path/to/your/project/folder
   ```
   (Replace `path/to/your/project/folder` with the actual location where you saved the website files)

3. **Start the preview server**: Type this command and press Enter:
   ```
   hugo server -D
   ```

4. **View your website**: Open your web browser and go to:
   ```
   http://localhost:1313
   ```
   You should see your website! It will automatically update when you save changes to your files.

5. **Stop the preview**: When done, go back to the Command Prompt/Terminal and press `Ctrl+C`

---

## Step 5: Build the Website for Publishing

Once you're happy with your changes, you need to prepare them for uploading to the internet.

### How to Build

1. **Open Command Prompt/Terminal**

2. **Navigate to your project folder**:
   ```
   cd path/to/your/project/folder
   ```

3. **Build the website**: Type this command and press Enter:
   ```
   hugo --gc --minify
   ```
   This creates all the files needed for the website. The generated files will be put in a folder called `public/`. You don't need to do anything with this folder—it's just for reference.

---

## Step 6: Upload Your Changes to the Internet

Once you've edited your content and built the website, you need to upload your changes so they appear on the live website.

### How to Upload Using GitHub

1. **Open GitHub Desktop** (or use the command line if you prefer):
   - Download GitHub Desktop from https://desktop.github.com if you don't have it
   - Install it and sign in with your GitHub account

2. **Open your project** in GitHub Desktop:
   - Click "File" → "Clone Repository"
   - Or if you already cloned it, click "Current Repository" and open your project folder

3. **See your changes**: GitHub Desktop will show all the files you've changed

4. **Write a description** (commit message):
   - In the bottom left, type a brief message describing what you changed
   - Example: "Updated team member bios" or "Changed contact information"

5. **Click "Commit to main"**: This prepares your changes

6. **Click "Push origin"**: This uploads your changes to GitHub and updates the live website!

---

## Quick Summary of the Process

1. Download Hugo
2. Download your project files from GitHub
3. Edit files in the `content/` folder
4. Preview locally with `hugo server -D`
5. Build with `hugo --gc --minify`
6. Upload changes to GitHub using GitHub Desktop or command line
7. Done! Your website is updated

---


## Getting Help

- If you get error messages, read them carefully—they usually tell you what's wrong
- Ask team member who knows tech for help

Don't be afraid to ask questions! Everyone starts as a beginner. Or ask chatgpt it will definitely help you out.