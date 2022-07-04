```
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/iamsajithsasi/python_foundation_program_Q2_APAC.git
git push -u origin main


git checkout -b develop

git checkout -b develop_new develop (Added first line and pushed)

git checkout develop (Cloned project and switch to develop)
git checkout -b develop_cloned develop (Added new line different from first branch)

git checkout develop
git merge develop_new
git merge develop_cloned (resolved conflict)
```