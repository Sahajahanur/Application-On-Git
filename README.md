# Git Merge & Conflict Tutorial — Developer A & Developer B Workflow

This repository demonstrates a real-world Git workflow involving:

- Cloning the same repo in two separate folders  
- Creating feature branches  
- Making independent changes as two developers  
- Pushing changes to GitHub  
- Pulling remote updates  
- Creating a merge conflict  
- Manually resolving the conflict  
- Finalizing the merge and pushing the resolved version

---

## 🏗 Project Setup

Two working directories were used to simulate two developers:

Developer A: D:\CODEBASICS\GIT\GIT_MERGE_AND_CONFLICT\Developer A

Developer B: D:\CODEBASICS\GIT\GIT_MERGE_AND_CONFLICT\Developer B

Both developers cloned the same repository:

     git clone https://github.com/Sahajahanur/Application-On-Git.git
##  1. 👨‍💻 Developer A Workflow
    cd /d D:\CODEBASICS\GIT\GIT_MERGE_AND_CONFLICT\Developer A\Application-On-Git

## 2. Create & switch to Developer A branch
    git branch developera
    git checkout developera

 ## 3. 3. Modify README.md
    adding Developer A Story

 ## 4. Commit changes
    git add .
    git commit -m "Developer A story"
 ## 5. Merge Developer A branch to main
    git checkout main
    git merge developera

## 6. Push to GitHub
    git push origin main

## 👨‍💻 Developer B Workflow
### 1. Navigate to Developer B repository
    cd /d D:\CODEBASICS\GIT\GIT_MERGE_AND_CONFLICT\Developer B\Application-On-Git

## 2. Create & switch to Developer B branch
    git branch developerb
    git checkout developerb
## 3. Modify README.md
    Update Application-On-Git Developer B
## 4. Commit changes
    git add .
    git commit -m "Developer B commit"
## 5. Merge into Developer B’s main (fast-forward merge)    
    git checkout main
     git merge developerb
## 6. Try to push — rejected (expected)     
    git push origin main
### GitHub returns:
       ! [rejected] main -> main (fetch first)
Reason:

Remote (GitHub) main contains Developer A's changes which are missing in Developer B’s local main.       

## ⚔️ Creating the Merge Conflict
### Developer B pulls from remote main:
    git pull
Git shows:

      CONFLICT (content): Merge conflict in README.md
     Automatic merge failed; fix conflicts and then commit the result.

Conflict markers in README.md:

       <<<<<<< HEAD
    (Developer B content)
     =======
    (Developer A content)
    >>>>>>> commit-hash

## 🛠 Resolving the Merge Conflict
 Developer B manually edited README.md to the final version:

     Update Application-On-Git Developer B
    adding Developer A Story

 ## Stage resolved file

    git add README.md

 ## Commit merge resolution
    git commit -m "Resolved merge conflict in README.md"
 ## Push final merged version
    git push origin main

 ## ✅ Final Result
 * Developer A’s changes merged
 * Developer B’s changes merged
 * Conflict resolved manually
 * Clean final README now visible on GitHub

Final README content:

    Update Application-On-Git Developer B
    adding Developer A Story

## 🎯 What This Tutorial Demonstrates
* Git clone
* Branch creation
* Independent development workflow
* Pushing changes
* Remote rejection (fetch-first)
* Merge conflict creation
* Conflict resolution
* Merge finalization

### This is a complete real-world Git workflow used by professional developers.

## 📌 Essential Git Commands Summary
    git clone <repository>
    git branch <branch-name>
    git checkout <branch-name>
    git add .
    git commit -m "message"
    git merge <branch>
    git pull
    git push origin <branch>


  





           

