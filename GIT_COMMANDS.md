# Git Commands

- Git & Github Workflow

![Git & Github Workflow](https://i.imgur.com/3Y0oCx6.png)

- Branches

![Branches](https://i.imgur.com/QtsQG8O.png)

- [Repository initialization](#repository-initialization)
- [Common Git commands](#common-git-commands)

## Repository Initialization

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

## Common Git Commands

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
