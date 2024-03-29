[Back](https://github.com/dawudg/pt-git-workshop/blob/main/ISSUES.md) - [Next](https://github.com/dawudg/pt-git-workshop/blob/main/PULL_REQUESTS.md)

# Git Branches

Git branches allow multiple parallel lines of development within a project.
They enable users to work on features or fixes without affecting the main codebase, promoting collaboration and experimentation.
Branches facilitate testing new ideas or isolating changes before merging them into the main branch.
They are a fundamental aspect of version control in Git, offering flexibility and organization to development workflows.

![Branches](https://i.imgur.com/QtsQG8O.png)

- [Naming conventions for branches and commits](#naming-conventions-for-branches-and-commits)
- [Creating Branches](#creating-branches)
- [Deleting Branches](#deleting-branches)
- [Merging Branches](#merging-branches)
- [Merge vs Rebase](#merge-vs-rebase)


## Naming conventions for branches and commits

### Branches:
- **Feature Branches:** 
  - Example: `feature/new-login-page`
  - Explanation: Feature branches are used to develop new features. They start with `feature/` followed by a descriptive name indicating the feature being worked on. In this example, the branch is created to implement a new login page.

- **Bug Fix Branches:** 
  - Example: `bug/fix-navigation-bug`
  - Explanation: Bug fix branches are created to address specific issues or bugs. They begin with `bug/` followed by a brief description of the bug being fixed. In this example, the branch is dedicated to fixing a navigation bug.

- **Release Branches:** 
  - Example: `release/v1.2.0`
  - Explanation: Release branches are used to prepare a new version of the software for deployment. They start with `release/` followed by the version number. In this example, the branch is created for version 1.2.0 of the software.

- **Hotfix Branches:** 
  - Example: `hotfix/typo-fix`
  - Explanation: Hotfix branches are created to quickly address critical issues in the production environment. They start with `hotfix/` followed by a brief description of the problem being fixed. In this example, the branch is dedicated to fixing a typo that requires immediate attention.

### Commits:
- **Commit Messages:** 
  - Example: `Fix typo in README.md`
  - Explanation: Commit messages should start with a capitalized verb in the imperative mood, succinctly describing the action taken in the commit. In this example, the commit message clearly indicates that a typo in the README.md file has been fixed.

- **Detailed Description:** 
  - Example: 
    ```
    Implemented login functionality using JWT for secure authentication.
    
    - Added login form component
    - Integrated JWT authentication with backend API
    - Implemented error handling for authentication failures
    ```
  - Explanation: The detailed description provides additional context or details about the changes made in the commit. It can include bullet points or paragraphs explaining the modifications in more depth. In this example, the description elaborates on the specific steps taken to implement the login functionality using JWT for secure authentication.

- **References:** 
  - Example: `Fixes #123`
  - Explanation: Including references to relevant issues or tickets helps in tracking changes and maintaining traceability. In this example, the commit message includes a reference to issue number 123, indicating that the commit addresses that specific issue.


## Creating Branches

### Local Branch:

#### Create a New Local Branch:
To create a new branch locally, you can use the `git branch` command followed by the branch name.

```bash
git branch <branch_name>
```

#### Checkout to Local Branch:
To change the branch you're working on, you can use the `git checkout` command followed by the branch name.

```bash
git checkout <branch_name>
```

Alternatively you can use this command to create & checkout to that branch faster.
```bash
git checkout -b <branch_name>
```

### Remote Branch:

#### Push from Local Branch:
To create a corresponding remote branch from your local repository, you can push to the remote repository (while inside that branch) by also adding the origin in addition to the push command.

```bash
git push origin <branch_name>
```

#### Creating a new branch on Github:
If you want to create a new branch directly on GitHub without first creating it locally, you can do so through the GitHub interface. Navigate to your repository on GitHub, then click on the "Branch" dropdown and type in the name of your new branch. Finally, click on the "Create branch" button.

#### Switching to a Remote Branch:
After creating a new branch on GitHub, you can switch to it locally by fetching the remote branches and checking out the desired branch.

```bash
git fetch origin
git checkout <remote_branch_name>
```

#### Syncing Local and Remote Branches:
To fetch the latest changes from a remote branch and merge them into your current local branch, use the `git pull` command.

```bash
git pull origin <branch_name>
```


## Deleting Branches

### Local Branch:

#### Delete a Merged Branch:
To delete a local branch that has been merged into the main branch (e.g., `main` or `master`), you can use the `git branch` command with the `-d` option followed by the branch name.

```bash
git branch -d <branch_name>
```

#### Delete an Unmerged Branch:
To delete a local branch that hasn't been merged into the main branch, you can use the `git branch` command with the `-D` option instead.

```bash
git branch -D <branch_name>
```


## Merging Branches

### Merge Local Branch into Main Branch:

1. Before merging a branch into the main branch (e.g., `main` or `master`), ensure you're on the target branch.

```bash
git checkout main
```

2. Now you can use the `git merge` command.

```bash
git merge <branch_name>
```

3. Resolve conflicts (if any). If Git encounters conflicts during the merge process, it'll pause and prompt you to resolve them. Use git status to identify conflicted files.

```bash
git status
```

4. After resolving all conflicts, you can stage the changes and make a commit.

```bash
git add <conflicted_file>
git commit -m "Merge <branch_name> into main"
```

### Merge Remote Branch into Local Branch:

1. Before merging changes from a remote branch into your local branch, ensure you have the latest updates.

```bash
git fetch origin
```

2. Merge the changes from the remote branch into your local branch using the `git merge` command.

```bash
git merge origin/<remote_branch_name>
```

3. After merging branches locally, push the changes to the remote repository to synchronize.

```bash
git push origin main
```

(replace main with the target branch of your remote repository)


## Merge vs Rebase

![Merge vs Rebase](https://i.imgur.com/tRSxtjg.png)

### Merge

#### Pros:
- Preserves the history of commits on both branches.
- Suitable for preserving chronological order of changes.
- Easy to understand and execute.

#### Cons:
- Results in a more cluttered commit history, especially in long-running projects.
- Can lead to "merge commits" that only serve to denote the merge itself, making the history less linear.


### Rebase

#### How it Works:
- Rebase integrates changes by moving the entire feature branch to the tip of the branch you're rebasing onto.
- It rewrites the commit history, applying each commit from the feature branch onto the tip of the target branch one by one.

#### Pros:
- Results in a cleaner and more linear commit history.
- Helps maintain a clearer chronological order of changes.
- Reduces the clutter of unnecessary merge commits.

#### Cons:
- Alters the commit history, which can cause conflicts if the rebased branch has been shared with others.
- Should not be used on public branches or branches shared among multiple developers without coordination.


### Choosing Between Merge and Rebase:

#### Use Merge When:
- Collaborating with others on a shared branch.
- Preserving the original commit history is important.
- Handling complex merge scenarios or when conflicts are expected.

#### Use Rebase When:
- Working on a feature branch alone or on private branches.
- Wanting to maintain a clean and linear commit history.
- Preparing a feature branch for a clean merge into the main branch.
