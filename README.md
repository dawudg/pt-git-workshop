# Git Intro

## Points of discussion during presantation

### Topics

- What is and why do we need version control?
- What is Git?
  - mention git's use case a version control manager, and also a collaboration tool
- What is Github and how is it different from Git?
  - mention alternatives to github
- Basic uses of git:
  - repo initialization
  - tracking local changes in 3 stages: working files, staged changes and commits
  - .gitignore file, also mention some examples where .gitignore would be useful
  - git workflow / most common scenarios (use a good image visualizing source code version work tree with branches commits and all that stuff):
    - cloning a repository
    - creating branches locally
      - mention standard branch use cases like having a development branch, separate one for each significant feature and naming conventions (feat/..., chore/..., fix/...)
    - adding or removing files to staged
    - making commits
      - mention standard for commit names
    - pushing and it's different options
    - stashing changes
    - merging branches (locally), and mention merge conflicts (also best practices on how to resolve them)
      - mention rebasing
    - pulling changes with `git pull`
- Collaborating on Github
- Github Branches (cloud)
- Github Pull Requests
  - Reviewing and approving a pull request on Github
- Github Issues
- Github Actions (brief introduction)
- Github profile improvements for better chances on getting a job:
  - a lot of commit activity / contributions
    - personal projects
    - open source
      - introduction to contributing open source
  - number of repositories
  - custom markdown file to show in profile

## Git Intro

- [Git installation](#git-installation)
- [Git user configuration](#git-user-configuration)
- [Repository initialization](#repository-initialization)
- [Common Git commands](#common-git-commands)

### Git Installation

1. You can download **Git** [here](https://git-scm.com/download) and then select your operating system to download.
2. Follow the necessary installer guide until installation is complete. Open the command prompt (Windows) or terminal (MacOS, Linux) and type `git version` to verify that **Git** was successfully installed.

### Git User Configuration

1. To set your **Git** username, type this in your terminal:

```shell
git config --global user.name "User Name"
```

- To confirm that you have set your **Git** username correctly, type this:

```shell
git config --global user.name
```

2. To set your **Git** email, type this in your terminal:

```shell
git config --global user.email "youremail@gmail.com"
```

- To confirm that you have set your **Git** email correctly, type this:

```shell
git config --global user.email
```

### Repository Initialization

1. Create **Github** Repository by going to your repositories page on **Github** and click on **"new"** or open this [link](https://github.com/new).
2. After filling in the repository name and chose it's visibility setting, click on **"Create Repository"**.
3. On the root folder of your project you want to open the terminal and type this:

```shell
git init
```

4. Create a **.gitignore** file in your folder.
5. After making the necessary changes to your .gitignore file add all the current working files in **"staging"** by using this command:

```shell
git add .
```

6. Create default branch:

```shell
git branch -M main
```

7. Add remote origin by providing the link to your **Github** repository:

```shell
git remote add origin https://github.com/username/repo-name.git
```

8. Push your changes:

```shell
git push -u origin main
```

### Common Git Commands

1. Initialize repository.

```shell
git init
```

2. Add all working changes to staged.

```shell
git add .
```

3. Commit all staged changes.

```shell
git commit -m "commit message"
```

4. Commit all working files, skip staging process completely

```shell
git commit -a -m "commit message"
```

5. Push commits to cloud repository (Github).

```shell
git push
```

6. Force push commits when normal pushing fails because of merge conflicts (avoid using).

```shell
git push --force
```

7. List all local branches.

```shell
git branch
```

8. Create new local branch.

```shell
git branch branchname
```

9. Delete local branch.

```shell
git branch -D branchname
```

10. Switch to different branch, when doing this make sure you either commit or stash current changes.

```shell
git checkout branchname
```

11. Switch to different branch, when doing this make sure you either commit or stash current changes.

```shell
git merge branchname
```

12. Stash changes.

```shell
git stash
```

add `--include-untracked` to include newly created files.

```shell
git stash --include-untracked
```

13. Unstash stashed changes.

```shell
git stash pop
```
