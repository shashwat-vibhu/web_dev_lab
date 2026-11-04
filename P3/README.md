# P3 – Feature Branch Git Workflow

## Aim
Create a feature branch, commit a change and merge it into main.

## Commands
```bash
git switch -c feature/about-section
git status
git add .
git commit -m "Add about section"
git switch main
git merge feature/about-section
git push origin main
```

## Explanation
A branch lets you work on a change separately. After committing it, merge the branch into main.