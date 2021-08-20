# GitFlow

Example to use Gitflow on GitHub
reference: [https://nvie.com/posts/a-successful-git-branching-model/](https://nvie.com/posts/a-successful-git-branching-model/)

## Steps to do after clone the repo the first time

- Create **develop** branch: `git checkout -b develop`
- Check branch: `git branch`
- Upload branch to github: `git push -u origin develop`

## Example: Table of Changes

|     ID    |           Description              |      Branch Gitflow                | Branch Start | Branch End       |
|-----------|:----------------------------------:|:-----------------------------------|:------------:|:----------------:|
| Change #1 |Login with Facebook                 | **feature**/login-with-facebook    | develop      | develop          |
| Change #2 |Export report of users              | **feature**/export-report-of-users | develop      | develop          |
| Change #3 | Error login with linkedin (v1.1.0) | **hotfix**/login-linkedin          | main         | main and develop |
| Change #4 | release version (v1.2.0)           | **release**/v1.2.0                 | develop      | main and develop |

## *Working with **feature**, using develop branch*

### Change #1 Developer 1

- Create the branch for the feature: `git checkout -b feature/login-with-facebook`
- Check branch: `git branch`
- Developing in the change: Create a file  `touch login-with-facebook.txt`
- Add changes: `git add login-with-facebook.txt` or we could use `git add .` to add all files
- Review files: `git status`
- Add commit: `git commit -m "Implement login with facebook"`
- Upload branch to github: `git push -u origin feature/login-with-facebook`
- Make pull request Respository->Pull Requests->
  - Base: **develop**
  - Compare: **feature/login-with-facebook**
  - Merge pull Request

### Change #2 Developer 2

- Begin since develop branch `git checkout develop`
- Update branch `git pull origin develop`
- Create the branch for the feature: `git checkout -b feature/export-report-of-users`
- Check branch: `git branch`
- Developing in the change: Create a file  `touch export-report-of-users.txt`
- Add changes: `git add export-report-of-users.txt` or we could use `git add .` to add all files
- Review files: `git status`
- Add commit: `git commit -m "Implement Export Report of Users"`
- Upload branch to github: `git push -u origin feature/export-report-of-users`
- Make pull request Respository->Pull Requests->
  - Base: **develop**
  - Compare: **feature/export-report-of-users**
  - Merge pull Request

## *Working with **hotfix**, using main branch*

### Change #3 Developer 3

- Begin since main branch `git checkout main`
- Update branch `git pull origin main`
- Create the branch for the feature: `git checkout -b hotfix/login-linkedin`
- Check branch: `git branch`
- Developing in the change: Create a file  `touch login-linkedin.txt`
- Add changes: `git add login-linkedin.txt` or we could use `git add .` to add all files
- Review files: `git status`
- Add commit: `git commit -m "Implement Login Linkedin"`
- Upload branch to github: `git push -u origin hotfix/login-linkedin`
- Make pull request Respository->Pull Requests->
  - Base: **main**
  - Compare: **hotfix/login-linkedin**
  - Merge pull Request

### Releases

- Pass main branch: `git checkout main`
- Update main branch: `git pull origin main`
- Add Version tag: `git tag -a v1.1.0 -m "version 1.1.0"`
- Upload : `git push -u origin v1.1.0`

### Pull Request over develop

- Respository->Pull Requests->
  - Base: **develop**
  - Compare: **main**
  - Merge pull Request
- Review develop `git checkout develop`
- Update develop `git pull origin develop`

## *Working with **release***

### Change #4 Developer 4

- Begin since develop branch `git checkout develop`
- Update branch `git pull origin develop`
- Create the branch for the release: `git checkout -b release/v1.2.0`
- Check branch: `git branch`
- Developing in the change: Create a file  `touch release.txt`
- Add changes: `git add release.txt` or we could use `git add .` to add all files
- Review files: `git status`
- Add commit: `git commit -m "File fixes release"`
- Upload branch to github: `git push -u origin release/v1.2.0`
- Make pull request Respository->Pull Requests->
  - Base: **main**
  - Compare: **release/v1.2.0**
  - Merge pull Request

### Releases 2

- Pass main branch: `git checkout main`
- Update main branch: `git pull origin main`
- Add Version tag: `git tag -a v1.2.0 -m "version 1.2.0"`
- Upload : `git push -u origin v1.2.0`

### Pull Request over develop Release

- Respository->Pull Requests->
  - Base: **develop**
  - Compare: **main**
  - Merge pull Request
- Review develop `git checkout develop`
- Update develop `git pull origin develop`
