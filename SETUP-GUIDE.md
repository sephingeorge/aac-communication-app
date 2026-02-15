# Git & GitHub Setup Guide

This guide will help you set up your local repository and push it to GitHub.

## Prerequisites Checklist

- [ ] Git installed on your computer
- [ ] GitHub account created
- [ ] Project files downloaded to your computer

---

## Step 1: Install Git (if needed)

### Windows
1. Download Git from: https://git-scm.com/download/win
2. Run the installer
3. Use default settings (click "Next" through the installer)
4. Open "Git Bash" from Start menu to verify installation

### macOS
**Option 1 - Using Homebrew (recommended):**
```bash
brew install git
```

**Option 2 - Download installer:**
1. Download from: https://git-scm.com/download/mac
2. Run the installer

**Option 3 - Install Xcode Command Line Tools:**
```bash
xcode-select --install
```

### Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install git
```

### Verify Git Installation
Open terminal/command prompt and run:
```bash
git --version
```
You should see something like: `git version 2.x.x`

---

## Step 2: Configure Git

Open terminal/command prompt and set your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Note**: Use the same email as your GitHub account.

---

## Step 3: Create GitHub Account (if needed)

1. Go to: https://github.com/signup
2. Follow the signup process
3. Verify your email address
4. Complete your profile

---

## Step 4: Set Up Local Repository

### 4.1 Create Project Folder
```bash
# Navigate to where you want your project
cd ~/Documents  # or wherever you prefer

# Create project folder
mkdir aac-communication-app
cd aac-communication-app
```

### 4.2 Add Your Files
Copy these files into your `aac-communication-app` folder:
- `aac-communication-app.html`
- `README.md`
- `.gitignore`
- `LICENSE`

### 4.3 Initialize Git Repository
```bash
# Initialize git in this folder
git init

# Check status (you should see untracked files)
git status

# Add all files to staging
git add .

# Commit the files
git commit -m "Initial commit: AAC Communication Helper app"
```

---

## Step 5: Create GitHub Repository

### Option A: Using GitHub Website (Easier)

1. Go to: https://github.com/new
2. Fill in repository details:
   - **Repository name**: `aac-communication-app`
   - **Description**: "Child-friendly AAC communication web app for children with autism"
   - **Visibility**: Choose Public or Private
   - **DO NOT** check "Initialize with README" (we already have one)
3. Click "Create repository"

### Option B: Using GitHub CLI (Advanced)

If you have GitHub CLI installed:
```bash
gh repo create aac-communication-app --public --source=. --remote=origin --push
```

---

## Step 6: Push to GitHub

After creating the repository on GitHub, you'll see instructions. Use these commands:

```bash
# Add GitHub repository as remote
git remote add origin https://github.com/YOUR-USERNAME/aac-communication-app.git

# Verify remote was added
git remote -v

# Push your code to GitHub
git branch -M main
git push -u origin main
```

**Replace `YOUR-USERNAME`** with your actual GitHub username!

---

## Step 7: Verify Upload

1. Go to: `https://github.com/YOUR-USERNAME/aac-communication-app`
2. You should see all your files
3. The README.md will display on the repository homepage

---

## Common Commands for Future Updates

### Making Changes and Updating GitHub

```bash
# Check what files changed
git status

# Add all changed files
git add .

# Or add specific files
git add aac-communication-app.html

# Commit with a message describing changes
git commit -m "Added new feature: custom button categories"

# Push changes to GitHub
git push
```

### View Commit History
```bash
git log --oneline
```

### Create a New Branch (for experimenting)
```bash
git checkout -b feature-new-icons
```

### Switch Back to Main Branch
```bash
git checkout main
```

---

## Hosting Your App on GitHub Pages

Want to make your app accessible via URL? Enable GitHub Pages:

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Click "Pages" in left sidebar
4. Under "Source", select "main" branch
5. Click "Save"
6. Your app will be live at: `https://YOUR-USERNAME.github.io/aac-communication-app/aac-communication-app.html`

**Make it the default page:**
Rename `aac-communication-app.html` to `index.html`, then it will be accessible at:
`https://YOUR-USERNAME.github.io/aac-communication-app/`

---

## Troubleshooting

### "Permission denied" error when pushing
You may need to set up authentication:

**Option 1 - HTTPS with Personal Access Token:**
1. Go to: https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Give it a name, select "repo" scope
4. Copy the token
5. Use this token as password when git asks

**Option 2 - SSH (More secure, recommended):**
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@example.com"

# Copy public key
cat ~/.ssh/id_ed25519.pub

# Add to GitHub:
# Settings → SSH and GPG keys → New SSH key
# Paste the key and save

# Update remote to use SSH
git remote set-url origin git@github.com:YOUR-USERNAME/aac-communication-app.git
```

### "Not a git repository" error
Make sure you're in the right folder:
```bash
pwd  # shows current directory
cd path/to/aac-communication-app
```

### Files not showing up on GitHub
```bash
# Check if files are ignored
git status

# Check .gitignore file
cat .gitignore
```

---

## Need Help?

- **Git Documentation**: https://git-scm.com/doc
- **GitHub Guides**: https://guides.github.com/
- **GitHub Help**: https://docs.github.com/

---

## Next Steps

1. ✅ Set up Git locally
2. ✅ Create GitHub repository  
3. ✅ Push your code
4. 🎯 Enable GitHub Pages (optional)
5. 🎯 Share the link with others
6. 🎯 Continue improving the app
7. 🎯 Accept contributions from others

Happy coding! 🚀
