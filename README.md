mitanandeesh@Mitas-MBP git-workflow % git flow init        
Initialized empty Git repository in /Users/mitanandeesh/GetKnowledge/git-workflow/.git/
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master] main
Branch name for "next release" development: [develop] 

How to name your supporting branch prefixes?
Feature branches? [feature/] 
Release branches? [release/] 
Hotfix branches? [hotfix/] 
Support branches? [support/] 
Version tag prefix? [] v


The above command automatically switches into develop branch
After this 

git remote add origin https://github.com/nandeeshsu/git-workflow.git
git push -u origin main
git push -u origin develop


mitanandeesh@Mitas-MBP git-workflow % git flow feature start feature1_branch
M	README.md
Switched to a new branch 'feature/feature1_branch'

Summary of actions:
- A new branch 'feature/feature1_branch' was created, based on 'develop'
- You are now on branch 'feature/feature1_branch'

Now, start committing on your feature. When done, use:

     git flow feature finish feature1_branch

mitanandeesh@Mitas-MBP git-workflow % git status
On branch feature/feature1_branch
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")