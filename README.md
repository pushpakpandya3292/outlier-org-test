## Challenge Git Solution

This github repository contains the solution to the challenge of rebasing two pull requests into the `master` branch in a specified order given by Outlier-org as a test task. 

## Steps to Reproduce the Solution

## Step 1: Clone the Original Repository [Given by Outlier_org]
git clone https://github.com/outlier-org/challenge-git.git
cd challenge-git

## Step 2: Fetch only the Pull Requests Not all the info
git fetch origin pull/3/head:feat/add-base64-endpoint
git fetch origin pull/4/head:feat/add-user-agent-endpoint

## Step 3: Check Out the Master Branch [If not alreaedy on master branch]
git checkout master

## Step 4: Rebase the First Pull Request
git rebase feat/add-base64-endpoint

## If conflicts occur during the rebase, resolve them manually and then 
### git add <resolved_file_name> or git add .
### git rebase --continue

## Repeat until the rebase is complete.

## Step 5: Rebase the Second Pull Request
git rebase feat/add-user-agent-endpoint

## Again, resolve any conflicts same as above one 
## Repeat until the rebase is complete.

## Step 6: Verify the Commit Order
git log --oneline
## You should see:
### 1. feat: add base64 endpoint
### 2. feat: add user-agent endpoint
### 3. init

## Step 7: Push the Changes to New Repository
git remote set-url origin https://github.com/pushpakpandya3292/outlier-org-test
git push origin master


### Now open above  repository and go to master branch there you can see 3 commints and if you click on commits you will see 3 commits in particular order
