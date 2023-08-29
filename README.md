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

mitanandeesh@Mitas-MBP git-workflow %  git flow feature finish feature1_branch
Switched to branch 'develop'
Updating 57327fc..87be4a2
Fast-forward
 README.md | 42 ++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 42 insertions(+)
Deleted branch feature/feature1_branch (was 87be4a2).

Summary of actions:
- The feature branch 'feature/feature1_branch' was merged into 'develop'
- Feature branch 'feature/feature1_branch' has been removed
- You are now on branch 'develop'


mitanandeesh@Mitas-MBP git-workflow % git flow feature finish  feature/feature2_branch
No branch matches prefix 'feature/feature2_branch'
mitanandeesh@Mitas-MBP git-workflow % git flow feature finish feature2_branch 
Switched to branch 'develop'
Updating 87be4a2..60dcbdb
Fast-forward
 README.md | 15 ++++++++++++++-
 1 file changed, 14 insertions(+), 1 deletion(-)
Deleted branch feature/feature2_branch (was 60dcbdb).

Summary of actions:
- The feature branch 'feature/feature2_branch' was merged into 'develop'
- Feature branch 'feature/feature2_branch' has been removed
- You are now on branch 'develop'


mitanandeesh@Mitas-MBP git-workflow % git flow release start release-0.1.0
Switched to a new branch 'release/release-0.1.0'

Summary of actions:
- A new branch 'release/release-0.1.0' was created, based on 'develop'
- You are now on branch 'release/release-0.1.0'

Follow-up actions:
- Bump the version number now!
- Start committing last-minute fixes in preparing your release
- When done, run:

     git flow release finish 'release-0.1.0'

mitanandeesh@Mitas-MBP git-workflow % git status
On branch release/release-0.1.0
nothing to commit, working tree clean


mitanandeesh@Mitas-MBP git-workflow % git flow release start release-0.2.0 
Switched to a new branch 'release/release-0.2.0'

Summary of actions:
- A new branch 'release/release-0.2.0' was created, based on 'develop'
- You are now on branch 'release/release-0.2.0'

Follow-up actions:
- Bump the version number now!
- Start committing last-minute fixes in preparing your release
- When done, run:

     git flow release finish 'release-0.2.0'

     mitanandeesh@Mitas-MBP git-workflow % git flow release finish release-0.2.0    
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
Merge made by the 'ort' strategy.
 README.md         | 15 +++++++++++++++
 release-0.2.0.txt |  0
 2 files changed, 15 insertions(+)
 create mode 100644 release-0.2.0.txt
Switched to branch 'develop'
Merge made by the 'ort' strategy.
 README.md         | 15 +++++++++++++++
 release-0.2.0.txt |  0
 2 files changed, 15 insertions(+)
 create mode 100644 release-0.2.0.txt
Deleted branch release/release-0.2.0 (was 3911cf6).

Summary of actions:
- Latest objects have been fetched from 'origin'
- Release branch has been merged into 'main'
- The release was tagged 'vrelease-0.2.0'
- Release branch has been back-merged into 'develop'
- Release branch 'release/release-0.2.0' has been deleted

mitanandeesh@Mitas-MBP git-workflow % git status
On branch develop
nothing to commit, working tree clean


It seems that the remote feature branch is deleted only if you call git flow feature finish with -F.

However, this fetches the remote before finishing the feature. From the docs:

-F fetch from $ORIGIN before performing finish
Otherwise you can delete the remote branch manually with:

git push origin :feature/new


mitanandeesh@Mitas-MBP git-workflow % git branch -r
  origin/develop
  origin/feature/feature1_branch
  origin/feature/feature2_branch
  origin/main
  origin/release/release-0.1.0
  origin/release/release-0.2.0
mitanandeesh@Mitas-MBP git-workflow % git push origin :feature/feature1_branch 
To https://github.com/nandeeshsu/git-workflow.git
 - [deleted]         feature/feature1_branch
mitanandeesh@Mitas-MBP git-workflow % git push origin :feature/feature2_branch
To https://github.com/nandeeshsu/git-workflow.git
 - [deleted]         feature/feature2_branch
mitanandeesh@Mitas-MBP git-workflow % git push origin :release/release-0.1.0  
To https://github.com/nandeeshsu/git-workflow.git
 - [deleted]         release/release-0.1.0
mitanandeesh@Mitas-MBP git-workflow % git push origin :release/release-0.2.0 
To https://github.com/nandeeshsu/git-workflow.git
 - [deleted]         release/release-0.2.0


 mitanandeesh@Mitas-MBP git-workflow % git flow hotfix start rar-12345     
Switched to a new branch 'hotfix/rar-12345'

Summary of actions:
- A new branch 'hotfix/rar-12345' was created, based on 'main'
- You are now on branch 'hotfix/rar-12345'

Follow-up actions:
- Bump the version number now!
- Start committing your hot fixes
- When done, run:

     git flow hotfix finish 'rar-12345'