# 🧪 Practice Exercises for Git & GitHub Fundamentals

---

### Exercise 1 — Configuration Verification

**Goal**
Confirm that Git is installed and configure your global author identity.

**Starting point**
A terminal window open.

**Steps**

1. Verify the Git installation:

   ```bash
   git --version
   ```

2. Configure your global username:

   ```bash
   git config --global user.name "Your Name"
   ```

3. Configure your global email:

   ```bash
   git config --global user.email "you@example.com"
   ```

4. Verify the configuration:

   ```bash
   git config --list
   ```

<details>
<summary><b>Click to reveal the Result</b></summary>

Git displays its installed version, and the configuration list contains your configured `user.name` and `user.email`.

</details>

**What this teaches**
Initial Git installation verification and global author identity configuration.

---

### 🟢 Level 1 — Reproduce: First Commit Lifecycle

**Goal**
Recreate the basic Git workflow of creating a repository, tracking a file, staging it, and committing it.

**Starting point**
A terminal window open in a suitable directory.

**Steps**

1. Create and enter a new directory:

   ```bash
   mkdir demo-repo
   cd demo-repo
   ```

2. Initialize the Git repository:

   ```bash
   git init
   ```

3. Create a file:

   ```bash
   touch index.html
   ```

4. Check the repository status:

   ```bash
   git status
   ```

5. Stage the file:

   ```bash
   git add index.html
   ```

6. Commit the staged file:

   ```bash
   git commit -m "Add index.html"
   ```

<details>
<summary><b>Click to reveal the Result</b></summary>

`index.html` first appears as **untracked**, then becomes **staged**, and finally is included in the commit. After the commit, the working tree should be clean.

</details>

**What this teaches** The fundamental local Git workflow:

**Working Directory → Staging Area → Repository**

---

### 🟡 Level 2 — Modify: Bulk Staging

**Goal**
Practice staging multiple files at once with `git add .` and inspecting repository status using the short format.

**Starting point**
Inside the `demo-repo` repository after completing Level 1.

**Steps**

1. Create two new files:

   * `styles.css`
   * `index.html`

2. Check the compact repository status:

   ```bash
   git status -s
   ```

3. Stage all changes:

   ```bash
   git add .
   ```

4. Verify the staging state:

   ```bash
   git status -s
   ```

5. Commit the staged files:

   ```bash
   git commit -m "Add UI files"
   ```

<details>
<summary><b>Click to reveal the Result</b></summary>

Both files appear as new changes, become staged together with `git add .`, and are saved in a single commit. The repository should return to a clean working tree after the commit.

</details>

**What this teaches**
Bulk staging with `git add .` and the compact output format provided by `git status -s`.

---

### 🟠 Level 3 — From Scratch: Independent Repository Creation

**Goal**
Create a Git repository and make its first commit without relying on the previous exercise as a reference.

**Starting point**
A terminal prompt outside an existing Git repository.

**Steps**

1. Create and initialize a repository named `notes-app`:

   ```bash
   git init notes-app
   ```

2. Navigate into the repository:

   ```bash
   cd notes-app
   ```

3. Create a `README.md` file.

4. Stage the file:

   ```bash
   git add README.md
   ```

5. Create the initial commit:

   ```bash
   git commit -m "Initial commit: Add README"
   ```

<details>
<summary><b>Click to reveal the Result</b></summary>

A new Git repository named `notes-app` is created, `README.md` is tracked, and the initial snapshot is recorded successfully.

</details>

**What this teaches**
Independent use of Git repository initialization, staging, and committing.

---

### 🔴 Level 4 — Small Challenge: Tracking File Modifications

**Goal**
Observe how Git detects changes to a file that is already being tracked.

**Starting point**
The `notes-app` repository containing a committed `README.md`.

**Steps**

1. Modify `README.md` using a text editor, or replace its contents with:

   ```bash
   echo "# My Notes App" > README.md
   ```

2. Check the repository status:

   ```bash
   git status
   ```

   Notice that `README.md` is now reported as **modified** rather than **untracked**.

3. Stage the modified file:

   ```bash
   git add README.md
   ```

4. Commit the change:

   ```bash
   git commit -m "Update README content"
   ```

5. Check the status again:

   ```bash
   git status
   ```

<details>
<summary><b>Click to reveal the Result</b></summary>

Git recognizes the edited `README.md` as a **modified tracked file**, stages the modification, and records it in a new commit. The working tree should be clean afterward.

</details>

**What this teaches**
The difference between **untracked files** and **modifications to already tracked files**, along with the file lifecycle:

**Untracked → Tracked → Modified → Staged → Committed**

---
