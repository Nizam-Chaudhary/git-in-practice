# Git Mastery Lab: The "Coffee Shop" Project

Welcome to the hands-on lab. Instead of isolated commands, we will build a small project to see how Git works in a real-world workflow.

---

## Lab 1: Project Kickoff
**Objective:** Set up your workspace and understand the initial state.

**Scenario:** You've been hired to build a website for "The Daily Grind" coffee shop.

1. **Initialize:** Create a directory `daily-grind`, enter it, and initialize a Git repository.
2. **Configuration Check:** Ensure your `user.name` and `user.email` are set locally for this project.
   - *Command:* `git config user.name` / `git config user.email`
3. **First File:** Create a file `index.html` with the text `<h1>Welcome to The Daily Grind</h1>`.
4. **The Staging Dance:**
   - Check `git status`. Note that `index.html` is **untracked**.
   - Add it to staging. Check `git status` again. It's now **staged** (changes to be committed).
   - Commit it with the message `feat: initial project setup`.

**Verification:** Run `git log`. You should see your first commit with a unique hash.

---

## Lab 2: Daily Workflow & Inspection
**Objective:** Learn to track changes and inspect differences.

**Scenario:** You need to add a menu and a style guide.

1. **New Files:** Create `menu.txt` (list 3 coffees) and `styles.css` (empty).
2. **Batch Staging:** Use a single command to stage both files.
3. **Wait, I forgot something!** Before committing, add `body { background: #f0ebe3; }` to `styles.css`.
4. **Inspection:**
   - Run `git diff`. Why does it only show the change in `styles.css`?
   - Run `git diff --staged`. What does this show?
5. **Commit:** Commit all changes with `feat: add menu and basic styling`.

**Reflect:** What is the difference between the "Working Directory" and the "Staging Area" based on step 4?

---

## Lab 3: Fixing Mistakes (The Undo Lab)
**Objective:** Master the art of "oops" management.

**Scenario:** You accidentally added a secret file and messed up the menu.

1. **The Secret File:** Create `api_keys.json`. Add it to staging.
2. **Unstage:** Realize secrets shouldn't be staged! Use `git restore --staged api_keys.json` to move it back to the working directory.
3. **The `.gitignore`:**
   - Create a `.gitignore` file.
   - Add `api_keys.json` to it.
   - Run `git status`. Does the secret file still appear?
4. **Discarding Changes:**
   - Open `menu.txt` and delete everything. Save it.
   - Realize you made a mistake. Use `git restore menu.txt` to bring back the menu from the last commit.

---

## Lab 4: Branching & Feature Development
**Objective:** Work on new features without breaking the "production" (main) code.

**Scenario:** A client wants a "Loyalty Program" feature, but you must keep the main site stable.

1. **Create & Switch:** Create a branch `feat-loyalty` and switch to it in one command.
2. **Develop:** Create `loyalty.html` and add some content. Commit it.
3. **The Context Switch:** Switch back to the `main` branch.
   - Look at your folder. Is `loyalty.html` there? (It shouldn't be!)
4. **Emergency Fix:** While on `main`, modify `index.html` to fix a typo. Commit it.

---

## Lab 5: Integration (Merging & Conflicts)
**Objective:** Combine work and handle the inevitable conflicts.

**Scenario:** Time to bring the Loyalty Program into the main site.

1. **The Simple Merge:** Merge `feat-loyalty` into `main`. Since `main` and `loyalty` changed different files, this should be a "Fast-forward" or simple merge.
2. **Creating a Conflict:**
   - On `main`, change the shop name in `index.html` to "The Midnight Grind". Commit.
   - Create a branch `rename-test`. Switch to it.
   - In `index.html`, change the shop name to "Coffee Heaven". Commit.
3. **The Clash:** Switch back to `main` and try to merge `rename-test`.
4. **Resolution:**
   - Open `index.html`. Find the markers `<<<<<<<`, `=======`, `>>>>>>>`.
   - Choose one name, delete the markers, stage the file, and commit to finalize the merge.

---

## Lab 6: Advanced Efficiency (Stash & Worktrees)
**Objective:** Manage multiple tasks like a pro.

**Scenario:** You're in the middle of a big CSS refactor when your boss demands a 1-minute text change on `main`.

1. **The Messy State:** Modify `styles.css` with 5-6 lines of changes. **Do not commit.**
2. **The Stash:** You need a clean working directory to switch branches. Run `git stash`.
3. **Verify:** Run `git status`. It should be clean.
4. **The Worktree Alternative:** Instead of stashing, let's use a worktree for the quick fix.
   - `git worktree add ../emergency-fix main`
   - Go to that folder, fix a typo, commit, and come back.
5. **Pop the Stash:** Run `git stash pop` to get your CSS work back.

---

## Final Challenge: The "Time Machine"
1. Find the commit hash of your very first commit using `git log`.
2. Use `git checkout <hash>` to travel back in time.
3. Look at your files.
4. Use `git switch main` to return to the present.