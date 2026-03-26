# VS Code + Claude Code Setup Guide

> First-time setup - from zero to working Second Brain in 15 minutes.

---

## What You're Installing

**Visual Studio Code (VS Code)**: A free code editor (like a smart text editor)
**Claude Code**: AI assistant that works inside VS Code with your files

**Why not just use Claude Web?** Your Second Brain needs to read/write files on your computer. Claude Code can do this, Claude Web cannot.

**Time**: 15 minutes total

---

## Part 1: Install Visual Studio Code (5 minutes)

### Step 1: Download VS Code

1. Go to: https://code.visualstudio.com
2. Click the big blue "Download" button
   - **Mac**: Downloads "VSCode-darwin-universal.zip"
   - **Windows**: Downloads "VSCodeUserSetup-x64.exe"
   - **Linux**: Choose your distribution

### Step 2: Install VS Code

**On Mac**:
1. Open the downloaded .zip file (double-click)
2. Drag "Visual Studio Code.app" to your Applications folder
3. Open Applications → Double-click "Visual Studio Code"
4. If you see "cannot be opened because it is from an unidentified developer":
   - Right-click VS Code → Click "Open"
   - Click "Open" again in the dialog

**On Windows**:
1. Double-click the downloaded installer
2. Click "Next" through the setup wizard
3. **IMPORTANT**: Check these boxes during installation:
   - ✅ "Add to PATH" (makes terminal commands work)
   - ✅ "Create desktop icon" (optional, but helpful)
4. Click "Install" → Wait → Click "Finish"

**On Linux**:
```bash
# Ubuntu/Debian
sudo snap install code --classic

# Or download .deb from website and:
sudo dpkg -i code_*.deb
```

### Step 3: Verify VS Code Works

1. VS Code should open automatically
2. You'll see a "Welcome" screen
3. Close the welcome tab (little X on the tab)

**✅ Checkpoint**: VS Code is running

---

## Part 2: Install Claude Code (10 minutes)

### Step 4: Get Claude Code Extension

**Inside VS Code**:

1. Look at the left sidebar (vertical icons)
2. Click the **Extensions** icon (looks like 4 squares, one separated)
   - Or press: `Cmd+Shift+X` (Mac) / `Ctrl+Shift+X` (Windows)

3. In the search box at the top, type: **claude code**

4. Find "Claude Code" by Anthropic
   - Should show "Anthropic" as publisher
   - Has blue "Install" button

5. Click **Install**

6. Wait 10-30 seconds for installation

**✅ Checkpoint**: Extension shows "Installed" (not "Install")

### Step 5: Open Claude Code Panel

1. After installation, you'll see a Claude icon in the left sidebar (looks like a sparkle or Claude logo)
2. Click the Claude icon
3. A panel opens on the right side titled "Claude Code"

**✅ Checkpoint**: Claude panel visible on right

### Step 6: Authenticate with Claude

**First-Time Login**:

1. In the Claude panel, click **"Sign in with Claude"** button
2. Your web browser opens
3. Log in to Claude.ai (use your existing account)
   - Use the email you purchased with
   - Password: [your Claude password]
4. Click **"Authorize"** or **"Allow Access"**
5. Browser shows: "You can close this window"
6. Return to VS Code

**✅ Checkpoint**: Claude panel now shows "Start a conversation" instead of "Sign in"

### Step 7: Test Claude Code Works

In the Claude panel (right side):

1. Type in the message box: **"Hello, can you tell me what repository I'm in?"**
2. Press Enter
3. Claude should respond: "You're not currently in a repository" (because we haven't opened one yet)

**✅ Checkpoint**: Claude responds to your message

---

## Part 3: Open Your Second Brain Repository (5 minutes)

### Step 8: Clone Your Repository

**FIRST: Check if Git is Installed**

**On Mac**:
```bash
git --version
```
If installed: Shows "git version 2.x.x"
If not: Mac will prompt to install (click "Install")

**On Windows**:
```bash
git --version
```
If not installed:
1. Download from: https://git-scm.com/download/windows
2. Run installer, click "Next" through defaults
3. Restart VS Code after installation

---

**Open Terminal in VS Code**:
1. Top menu: **Terminal** → **New Terminal**
   - Or press: `` Ctrl+` `` on both Mac and Windows
2. A terminal panel opens at the bottom
3. You see a command prompt

**What terminal you'll see**:
- **Mac**: zsh or bash (both work the same)
- **Windows**: PowerShell (blue background) or Command Prompt (black background) - both work

**Clone Repository** (choose your operating system):

**On Mac / Linux**:
```bash
cd ~
mkdir -p repos
cd repos
git clone https://github.com/iwo-szapar/[your-repo-name]
```

**On Windows** (PowerShell or Command Prompt):
```bash
cd %USERPROFILE%
mkdir repos 2>nul
cd repos
git clone https://github.com/iwo-szapar/[your-repo-name]
```

**Replace `[your-repo-name]`** with your actual repository name (provided by Iwo)

**Note**: The `2>nul` suppresses "folder already exists" error (safe to ignore)

**What this does**:
- Goes to your home directory (`~` on Mac, `%USERPROFILE%` on Windows)
- Creates a "repos" folder (if doesn't exist)
- Downloads your Second Brain there

**Expected Output**:
```
Cloning into '[your-repo-name]'...
remote: Enumerating objects...
remote: Counting objects...
Receiving objects: 100%
```

**If you see "Permission denied" or "Authentication failed"**:

You need repository access first. Use the **Simpler Alternative** below.

---

**Simpler Alternative (Recommended for First-Timers)**:

This method works without git credentials:

1. Visit: `https://github.com/iwo-szapar/[your-repo-name]` (URL provided by Iwo)
2. If you see "404" - Ask Iwo to add you as collaborator first
3. Once you have access, click the green **"Code"** button
4. Click **"Download ZIP"**
5. Extract the ZIP file:
   - **Mac**: Double-click ZIP → Drag extracted folder to Documents
   - **Windows**: Right-click ZIP → "Extract All" → Choose location
6. Rename extracted folder to match your repo name (e.g., `yourname-second-brain`)
7. Move to:
   - **Mac**: `/Users/[yourusername]/repos/[your-repo-name]`
   - **Windows**: `C:\Users\[yourusername]\repos\[your-repo-name]`

**Note**: With ZIP method, you won't receive future updates automatically. Ask Iwo how to sync later.

### Step 9: Open Repository in VS Code

**In VS Code**:

1. Top menu: **File** → **Open Folder...**
   - Mac: Menu bar at top of screen
   - Windows: Menu bar at top of VS Code window

2. Navigate to your repository:

   **On Mac**:
   - Click your user folder in sidebar (shows house icon)
   - Find "repos" folder
   - Click your repository folder (e.g., "yourname-second-brain")
   - Click **"Open"**

   **On Windows**:
   - Navigate to: `C:\Users\[YourUsername]\repos`
   - Or type in address bar: `%USERPROFILE%\repos`
   - Click your repository folder (e.g., "yourname-second-brain")
   - Click **"Select Folder"**

3. **If VS Code asks "Do you trust the authors of files in this folder?"**:
   - Click **"Yes, I trust the authors"**
   - (This is your own repository, so it's safe)

**✅ Checkpoint**: You see files in the left sidebar:
- CLAUDE.md
- memory/ (folder)
- experiences/ (folder)
- agent_docs/ (folder)
- .claude/ (folder)

**If you don't see these files**: You opened the wrong folder. Try again and make sure you select the "maydogan-second-brain" folder specifically.

### Step 10: Verify Second Brain Works

**In Claude panel (right side)**:

Type:
```
/ask What is this repository about?
```

**Expected Response**:
Claude reads your CLAUDE.md and responds with personalized info about your podcast CRM automation system.

**✅ Checkpoint**: Claude knows about your podcast workflow

---

## Part 4: First Commands (2 minutes)

### Test Your Day-One Win

**Command 1: Project Status**
```
/ask What are all my current podcast projects and their status?
```

**Expected**: Claude explains it needs Airtable MCP to access your CRM (we'll set this up during onboarding call)

**Command 2: Brand Feedback** (after filling brand-promise.md)
```
/ask I'm considering inviting a crypto influencer to my podcast. Review this against my brand promise - be critical.
```

**Expected**: Claude checks memory/style-voice/brand-promise.md and provides feedback

**Command 3: Test Workflow**
```
/my-workflow "Research potential podcast guest on LinkedIn: [any name]"
```

**Expected**: Claude creates a plan → asks for approval → executes research

---

## Troubleshooting

### "Extension not found"
**Solution**: Make sure you searched for "claude code" exactly (two words)
**Check**: Publisher should be "Anthropic"

### "Can't sign in"
**Solution**:
1. Make sure you have a Claude.ai account
2. Try signing in to claude.ai in browser first
3. Then retry extension login

### "Repository not cloning"
**Solution**:
1. Check you have git installed: `git --version`
2. If not installed:
   - **Mac**: Run `git --version` and macOS will prompt to install
   - **Windows**: Download from https://git-scm.com/download/windows
3. Or use "Simpler Alternative" (Download ZIP) - no git needed

### "Claude says it can't access files"
**Solution**:
1. Make sure you opened the folder (File → Open Folder)
2. Not just opened a single file
3. Trust the folder when prompted

### "Commands not working"
**Solution**:
1. Make sure you're in the Claude panel (right side)
2. Not in the terminal panel (bottom)
3. Commands start with `/` like `/ask`

### "Too many windows open, confused"
**Solution**:
- Left sidebar: File explorer (your repository files)
- Right panel: Claude conversation (where you type commands)
- Bottom panel: Terminal (for git commands if needed)
- You'll mostly use the Claude panel (right)

---

## Quick Reference Card

### Essential Keyboard Shortcuts

| Action | Mac | Windows |
|--------|-----|---------|
| Open Command Palette | `Cmd+Shift+P` | `Ctrl+Shift+P` |
| Open Extensions | `Cmd+Shift+X` | `Ctrl+Shift+X` |
| Open Terminal | `` Ctrl+` `` | `` Ctrl+` `` |
| Close Tab | `Cmd+W` | `Ctrl+W` |
| Save File | `Cmd+S` | `Ctrl+S` |
| Toggle Sidebar | `Cmd+B` | `Ctrl+B` |

### Where to Type Commands

**❌ Wrong**: Terminal panel (bottom) - this is for git/system commands
**✅ Right**: Claude panel (right side) - this is for /ask, /my-workflow, etc.

---

## What's Next After Setup

### During Onboarding Call (with Iwo)
1. Set up Airtable MCP (15 min) - connects to your CRM
2. Set up Google Workspace MCP (10 min) - connects to Calendly
3. Run first automated CRM update (5 min)
4. Test Day-One Win capabilities (5 min)

### First Week Solo
Follow: `/first-week-onboarding` or read `quick-start/DAY-ONE-GUIDE.md`

**Daily tasks**: 5-10 min/day for 7 days
**Result**: Full automation working + brain learning your workflow

---

## System Requirements

**Minimum**:
- **OS**: macOS 10.15+, Windows 10+, or modern Linux
- **RAM**: 4 GB (8 GB recommended)
- **Disk Space**: 500 MB for VS Code + extensions
- **Internet**: Required (Claude runs in cloud)

**Your Setup**: Should work fine (you use Claude Web already)

---

## Alternative: If You Prefer Claude Web

**Can you use Claude Web instead of VS Code?**

**Limited functionality**:
- ✅ Can chat with Claude
- ✅ Can ask questions
- ❌ Can't access your local files
- ❌ Can't use skills or commands
- ❌ Can't run /my-workflow
- ❌ Can't automate CRM updates

**Recommendation**: Use VS Code for Second Brain work
- Use Claude Web for quick questions if needed
- But for podcast workflow automation, VS Code + Claude Code is required

---

## Getting Help

**During Setup**:
- Stuck? Take a screenshot and send to Iwo
- Or bring questions to onboarding call

**After Setup**:
- In Claude panel, type: `/ask How do I [whatever you're stuck on]?`
- Your brain has all setup documentation and can guide you

**Common Resources**:
- VS Code Docs: https://code.visualstudio.com/docs
- Claude Code Docs: https://claude.ai/code
- Your quick-start: `quick-start/DAY-ONE-GUIDE.md`

---

## Setup Checklist

Print or check off as you go:

### Part 1: VS Code
- [ ] Downloaded VS Code from code.visualstudio.com
- [ ] Installed VS Code on computer
- [ ] Opened VS Code successfully
- [ ] Saw Welcome screen

### Part 2: Claude Code
- [ ] Opened Extensions panel (Cmd+Shift+X or Ctrl+Shift+X)
- [ ] Searched for "claude code"
- [ ] Installed Claude Code extension
- [ ] Clicked Claude icon in left sidebar
- [ ] Signed in with Claude account
- [ ] Saw "Start a conversation" in panel

### Part 3: Repository
- [ ] Opened terminal in VS Code
- [ ] Cloned repository to ~/repos/maydogan-second-brain
- [ ] Opened folder in VS Code (File → Open Folder)
- [ ] Trusted the folder
- [ ] Saw files in left sidebar (CLAUDE.md, memory/, etc.)

### Part 4: Verification
- [ ] Typed `/ask What is this repository about?` in Claude panel
- [ ] Got personalized response about podcast CRM
- [ ] Ready for onboarding call

**When all checked**: ✅ Setup complete, ready to start!

---

**Created**: December 22, 2025
**For**: Mehmet Aydogan (first-time VS Code user)
**Estimated Time**: 15 minutes
**Difficulty**: Beginner-friendly
**Support**: Available during onboarding call
