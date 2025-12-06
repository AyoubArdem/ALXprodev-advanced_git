# ALXprodev-advanced_git

## 0) Setting up gitflow



```bash
mkdir ALXprodev-advanced_git
cd ALXprodev-advanced_git
git init

git remote add origin git@github.com:<your-username>/ALXprodev-advanced_git.git


git checkout -b main
git push -u origin main

git checkout -b develop
git push -u origin develop

echo "# ALXprodev-advanced_git" > README.md
git add README.md
git commit -m "chore: add README"
git push origin develop
```



## 1) Creating a feature branch


* commit message: `feat: scaffolding login page`
* push


```bash

git checkout develop

git checkout -b feature/implement-login

mkdir -p login-page
echo "Login Feature Coming soon" > login-page/README.md


git add login-page/README.md
git commit -m "feat: scaffolding login page"

git push -u origin feature/implement-login

 git push origin develop
```



## 2) Creating a Release Branch (release/1.0.0) and flow

```bash

git checkout develop
git checkout -b feature/implement-signup

mkdir -p signup-page
echo "feature coming soon" > signup-page/README.md

git add signup-page/README.md
git commit -m "feat: scaffolding signup page"
git push -u origin feature/implement-signup




git checkout develop
git merge --no-ff feature/implement-login -m "Merge feature/implement-login into develop"
git merge --no-ff feature/implement-signup -m "Merge feature/implement-signup into develop"

git push origin develop


git checkout -b release/1.0.0 develop


echo "feature coming soon" > signup-page/README.md

echo "data requirements: email, firstName, lastName, profilePic" >> signup-page/README.md

git add signup-page/README.md
git commit -m "chore: update signup README for release 1.0.0"
git push -u origin release/1.0.0

git checkout main
git merge --no-ff release/1.0.0 -m "Merge release/1.0.0 into main"
git checkout develop
git merge --no-ff release/1.0.0 -m "Merge release/1.0.0 into develop"


git tag -a v1.0.0 -m "Release v1.0.0"
git push origin main
git push origin develop
git push origin --tags
```
