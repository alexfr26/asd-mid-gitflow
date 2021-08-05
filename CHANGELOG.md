# ASD 1: Git Workflow

### 1. Create a new repo on GitHub

- [x] created new repo in GitHub (https://github.com/alexfr26/asd-mid-gitflow.git)

### 2. Create file CHANGELOG.md with just a tittle and push it to master

- [x] git init && git branch -M master
- [x] git remote add origin https://github.com/alexfr26/asd-mid-gitflow.git
- [x] echo "# ASD 1: Git Workflow" >> CHANGELOG.md
- [x] git add CHANGELOG.md && git commit -m "initial commit"
- [x] git push origin master

### 3. Create a new branch develop from master

- [x] git switch -c develop

### 4. Create three new branches from develop, feature-one, feature-two, feature-three

- [x] git branch feature-one && git branch feature-two && git switch -c feature-three

### 5. On branch feature-three make 3 commits, each of these commits should add new content to the file f3.txt: f3.1, f3.2, f3.3

- [x] echo "f3.1" >> f3.txt && git add f3.txt && git commit -m "created f3 -> f3.1"
- [x] echo "f3.2" >> f3.txt && git add f3.txt && git commit -m "updated f3 -> f3.2"
- [x] echo "f3.3" >> f3.txt && git add f3.txt && git commit -m "updated f3 -> f3.3"

### 6. On branch feature-one make two commits adding to file f1.txt next content: f1.1, f1.2

- [x] git switch feature-one
- [x] echo "f1.1" >> f1.txt && git add f1.txt && git commit -m "created f1 -> f1.1"
- [x] echo "f1.2" >> f1.txt && git add f1.txt && git commit -m "updated f1 -> f1.2"

### 7. On branch feature-two make two commits adding to file f2.txt next content: f2.1, f2.2

- [x] git switch feature-two
- [x] echo "f2.1" >> f2.txt && git add f2.txt && git commit -m "created f2 -> f2.1"
- [x] echo "f2.2" >> f2.txt && git add f2.txt && git commit -m "updated f2 -> f2.2"

### 8. Using cherry-pick transfer second commit from feature-tree branch to feature-one branch

- [x] git switch feature-one
- [x] git log --oneline feature-three (to take sha1 of the 2nd commit) // ac753b5
- [x] git cherry-pick ac753b5 // confict appeared
- [x] git add f3.txt // resolve it by adding the file to the curent git branch
- [x] git cherry-pick --continue // can rename commit

### 9. Create a new hotfix branch from master called hotfix-one, create file hotfix.txt with content: hotfix

- [x] git switch -c hotfix-one master
- [x] echo "hotfix" >> hotfix.txt && git add hotfix.txt && git commit -m "hotfix"

### 10. Merge this branch into master and develop

- [x] git switch master && git merge hotfix-one
- [x] git switch develop && git merge hotfix-one
- [x] git branch -d hotfix-one // delete if this branch is not needed

### 11. Using rebase sync branch feature-one and develop

- [x] git switch feature-one && git rebase develop

### 12. Merge branch feature-one into develop using squash method

- [x] git switch develop && git merge --squash feature-one
- [x] git commit -m "merged feature-one branch using squash"

### 13. Using rebase sync branch feature-two with develop

- [x] git switch feature-two && git rebase develop

### 14. Merge branch feature-two with develop using squash

- [x] git switch develop && git merge --squash feature-two
- [x] git commit -m "merged feature-two branch using squash"

### 15. Make a release of the latest changes on develop

- [x] git switch master && git merge --squash develop
- [x] git commit -m "merged develop branch"
- [x] git push origin master
- [x] on GitHub page create new release
