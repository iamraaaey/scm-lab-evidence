# Session 1 Reflection

### Q1. Why is a commit history useful when maintaining software? Give one concrete maintenance situation (for example finding when a bug appeared) and refer to your own commits.
A commit history provides an immutable, chronological audit trail of all changes made to a software system, detailing what was altered, who made the change, when, and why. In software maintenance, if a defect or regression is detected in production, developers can navigate the history (e.g., using `git log` or `git bisect`) to identify the exact commit that introduced the bug instead of guessing across thousands of lines of code. For instance, in our repository, each commit is atomic: commit `a23a9c5` introduced the initial README, `765090a` added student identification details, and `7704f48` isolated `.gitignore` configuration. If an issue occurred with untracked temporary files, maintainers can instantly inspect commit `7704f48` directly to review the rule definitions.

### Q2. Explain the difference between Git and GitHub, using your two repositories (the exercise repository and scm-lab-evidence) as examples.
Git is an open-source, local distributed version control software running directly on a computer's operating system to track code changes, branches, and commit histories offline without requiring a network connection. In contrast, GitHub is a cloud-based hosting service and collaboration platform that stores Git repositories online and provides project management tools such as pull requests, code reviews, issue trackers, and GitHub Actions automation. For example, our repository `scm-lab-evidence` was initialized, branched, and committed locally using Git command-line tools before being synchronized, whereas the `skills-introduction-to-github` repository leveraged GitHub's web interface, hosted pull request reviews, and automated bot workflows.

### Q3. In the GitHub Skills exercise you worked on a branch and used a pull request instead of changing main directly. What risk does this reduce?
Working on an isolated branch and submitting changes via a pull request prevents untested, incomplete, or defective code from directly destabilizing the production-ready `main` branch. It reduces the risk of merge conflicts and breaking regressions by creating a dedicated review checkpoint where team members can inspect the diff, discuss improvements, and verify functionality before merging. In the GitHub Skills exercise, developing on `my-first-branch` and reviewing via pull request ensured that changes were verified and approved prior to becoming part of the permanent baseline.

### Q4. State which of your commands changed only your computer and which changed GitHub.
Commands such as `git init`, `git add`, `git commit`, `git switch`, `git merge`, and `git restore` changed files, branches, and references solely within the local working tree and `.git` directory on my computer without sending data over the network. Conversely, commands such as `git push` (which uploaded our local branch commits to the remote), `git clone` (which copied the remote repository into a second directory), and `git pull` (which fetched and merged the simulated teammate commit back into our local repository) communicated with the remote server and altered or synchronized state with GitHub.

---

## Part 1 Concept Table

| Term | Your definition in one sentence |
| :--- | :--- |
| **Repository** | A project directory tracked by Git containing all project files and folders along with their complete historical versions. |
| **Working tree (working directory)** | The local filesystem directory containing the files currently checked out for viewing and editing. |
| **Staging area (index)** | An intermediate area that holds a formatted list of changes selected to be saved in the next commit. |
| **Commit** | A permanently saved snapshot of staged changes recorded in Git history with an author, timestamp, and descriptive message. |
| **Branch** | A lightweight, movable pointer to a line of commits that enables parallel, independent development. |
| **Merge** | The operation of combining commits and content from one branch into another branch. |
| **Remote** | A version of the repository hosted on an external server or network (such as GitHub) accessible by collaborators. |
| **Push / Pull / Clone** | `git push` uploads local commits to a remote repository; `git pull` downloads and integrates new remote commits locally; `git clone` creates a local copy of a remote repository for the first time. |
