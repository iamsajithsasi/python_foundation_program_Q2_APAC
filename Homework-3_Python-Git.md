# Python Practice - Session 3

1. Create a local folder and initialize it for git;
2. Create a text file in the folder and commit it;
3. Create a remote repository on GitHub;
4. Push the local repository to GitHub;
5. Create a new branch (develop) and switch to it;
6. Create a new branch from 'develop' and switch to it;
7. Add the first line in the text file, commit, and push to remote;
8. Clone your repository from GitHub into a separate folder;
9. Create another branch from 'develop' and switch to it using cloned project;
10. Add the first line of the text file (different from the first branch), 
    commit, and push on remote;
11. Switch to develop;
12  Merge the first branch and push changes;
13. Merge the second branch and push changes;
14. Resolve conflict;
16. Commit and push a separate text file with a list of all the commands, which were used to solve the problem;


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