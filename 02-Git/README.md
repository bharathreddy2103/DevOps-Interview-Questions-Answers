1. What is Git, and why is it important for DevOps?

Git is a distributed version control system that allows developers to track changes in source code during software development. In DevOps, Git is critical for enabling CI/CD pipelines, collaboration, and version tracking.

3. What is the difference between Git and GitHub?

Git: A version control system for tracking code changes.

GitHub: A cloud-based hosting platform for Git repositories, enabling collaboration and integration with tools.

3. What is the purpose of the .gitignore file?
The .gitignore file specifies files and directories that Git should ignore. For example, sensitive files, build artifacts, or logs can be excluded.

4. What is a branch in Git?
A branch is a pointer to a snapshot of your changes. Branches allow you to work on features or fixes without affecting the main codebase.

Command to create a branch: git branch feature_branch.

Switch to a branch: git checkout feature_branch.

5. What is the difference between git pull and git fetch?

git pull: Fetches changes from the remote repository and merges them into the current branch.

git fetch: Only downloads changes from the remote repository but does not merge them.

6. How do you resolve merge conflicts in Git?

Identify conflicts: Git marks conflicting files with conflict markers (<<<<<<<, =======, >>>>>>>).

Manually resolve conflicts by editing the files.

Stage the resolved files: git add file_name.

Commit the changes: git commit.

7. What is Git rebase, and how does it differ from Git merge?

Rebase: Moves or combines a sequence of commits to a new base commit, creating a linear history.

Merge: Combines two branches, preserving the commit history and creating a merge commit.

Example of rebase:

git checkout feature_branch  
git rebase main

8. How do you undo a commit in Git?

Undo the last commit but keep changes: git reset --soft HEAD~1.

Undo the last commit and discard changes: git reset --hard HEAD~1.

9. What is the purpose of Git stash?
Git stash temporarily saves changes that are not yet ready for a commit.

Save changes: git stash.

Apply stashed changes: git stash apply.

List stashes: git stash list.

10. What is a detached HEAD in Git, and how do you fix it?

Detached HEAD occurs when you check out a specific commit instead of a branch.

To fix:

Create a new branch: git checkout -b new_branch.

Or switch to a branch: git checkout branch_name.

11. How do you squash commits in Git?
Squashing combines multiple commits into one.

Command: git rebase -i HEAD~n (where n is the number of commits to squash).

In the interactive editor, mark commits as squash or s.

12. What are Git submodules?
Git submodules are repositories nested inside another repository. They allow managing dependencies as separate projects.

Add a submodule: git submodule add <repo_url>.

Update submodules: git submodule update --init.

13. Scenario: Your team accidentally commits sensitive information (like API keys) to the repository. How do you fix it?
Steps:

Remove the sensitive file from history:

git filter-branch --force --index-filter \
"git rm --cached --ignore-unmatch sensitive_file" \
--prune-empty --tag-name-filter cat -- --all

Push changes: git push origin --force --all.

Inform the team and revoke exposed keys.

14. Scenario: A developer force-pushed to the main branch and broke the repository. How do you recover?
Steps:

Identify the correct state using the reflog: git reflog.

Reset the branch to a working commit: git reset --hard commit_hash.

Force-push the corrected branch: git push --force.

15. Scenario: You want to migrate a repository from GitHub to GitLab. How do you handle this?
Steps:

Clone the GitHub repository: git clone --mirror <github_repo_url>.

Push to GitLab: git push --mirror <gitlab_repo_url>.

16. Scenario: You need to review a colleague's pull request and suggest changes.
Steps:

Fetch the pull request branch:

git fetch origin pull/<ID>/head:pr_branch  
git checkout pr_branch

Review and comment on changes directly in the pull request tool (e.g., GitHub/GitLab UI).

17. Scenario: A feature branch is behind the main branch. How do you update it?
Steps:

Use git pull to merge the main branch into the feature branch:

git checkout feature_branch  
git pull origin main

Or rebase the feature branch:

git checkout feature_branch  
git rebase main

18. What is the difference between git clone, git fork, and git init?

git clone: Creates a copy of an existing repository.

git fork: Copies a repository to your GitHub/GitLab account for independent development.

git init: Initializes a new Git repository locally.

19. How do you create a Git tag?

Lightweight tag: git tag tag_name.

Annotated tag: git tag -a tag_name -m "message".

Push tags: git push origin tag_name.

20. How do you manage large repositories with Git LFS?

Git LFS (Large File Storage) is used for managing large files.

Example:

git lfs install  
git lfs track "*.psd"  
git add .gitattributes
