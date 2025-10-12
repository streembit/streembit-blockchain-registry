# streembit-blockchain-registry
Streembit blockchain config and registry files

### Steps when released to public to have a clean commit history:

#### Create a new orphan branch (no history)
git checkout --orphan new-main

#### Stage all files
git add .

#### Create your single commit
git commit -m "Initial public release"

#### Delete the old main branch
git branch -D main

#### Rename new branch to main
git branch -m main

#### Force push to GitHub (replaces all history)
git push -f origin main
