git branch feature/add-readme-section
git checkout feature/add-readme-section


echo "New Section Content" >> README.md
git add README.md
git commit -m "Add new section to README"

git push origin feature/add-readme-section
git checkout main
git pull origin main

echo "Update content" >> README.md
git add README.md
git commit -m "Update README"
git push origin feature/add-readme-section

git checkout main
git merge feature/add-readme-section
git push origin main
git stash save "Тимчасове збереження змін для нової функції"
git stash list
git stash apply stash@{0}

