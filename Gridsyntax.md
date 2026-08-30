```text
============================================================
FLUTTER + GIT COMMANDS — QUICK REFERENCE
============================================================


------------------------------------------------------------
1. CREATE FLUTTER PROJECT IN CURRENT FOLDER
------------------------------------------------------------

flutter create --project-name litead_logic_games .

. = Create the Flutter project HERE in the current folder.

Example:
If terminal is already at:

C:\lite_ad_studios\games\litead_logic_games>

the project will be created inside that folder.


------------------------------------------------------------
2. BASIC GIT FLOW
------------------------------------------------------------

Check what changed:

git status


Stage ALL changed files:

git add .


Stage only one specific file:

git add lib/main.dart


Commit staged changes:

git commit -m "Meaningful comment"


Push main branch:

git push origin main


After upstream has already been configured, usually:

git push


Get latest changes:

git pull


------------------------------------------------------------
3. GIT USER CONFIGURATION
------------------------------------------------------------

Set identity ONLY for the current repository:

git config user.name "LiteAdGamingStudios"

git config user.email "208376080+itzriyas@users.noreply.github.com"


Set identity globally for all repositories:

git config --global user.name "Riyas Mohammed"

git config --global user.email "208376080+itzriyas@users.noreply.github.com"


Check global configuration:

git config --global --list


GitHub private email can be found under:

GitHub
→ Settings
→ Emails
→ Keep my email addresses private


------------------------------------------------------------
4. DISCARD AN UNCOMMITTED CHANGE
------------------------------------------------------------

Example:

git restore lib/main.dart

This discards the local uncommitted changes in main.dart and
restores the last Git version.

WARNING:
The discarded changes are lost.


------------------------------------------------------------
5. CREATE FILES USING POWERSHELL
------------------------------------------------------------

Create file using relative path:

New-Item -ItemType File -Path ".\AI_CONTEXT.md"


Create file using absolute path:

New-Item -ItemType File -Path "C:\lite_ad_studios\Utilities\FinanceTracker\scripts\gmail_download.py"


Show folder/file structure:

tree C:\lite_ad_studios\Utilities\FinanceTracker /F


============================================================
FULL FLOW — CREATE LOCAL PROJECT AND CONNECT TO GITHUB
============================================================


1. Create parent folder:

mkdir C:\Git


2. Move into it:

cd C:\Git


3. Create Flutter project:

flutter create --project-name git_testing GitTesting

git_testing = Dart/Flutter project name
GitTesting  = Windows folder name

Dart project names should use lowercase letters and underscores.


4. Move into project:

cd GitTesting


5. Initialize Git:

git init


6. Connect local project to GitHub:

git remote add origin https://github.com/itzriyas/GitTesting.git


Check the saved GitHub connection:

git remote -v


7. If GitHub already contains files such as README.md:

git pull origin main --allow-unrelated-histories

--allow-unrelated-histories is needed when the local project and
GitHub repository were created separately and therefore have
different starting histories.

If there is a conflict, resolve it before continuing.


8. Check files:

git status


9. Stage files:

git add .


10. Commit:

git commit -m "Add Flutter project"


11. If local branch is called master but GitHub uses main:

git branch -M main

-M = rename the current branch to main (force rename if necessary).


12. Push and establish upstream:

git push -u origin main

-u remembers:

local main → origin/main

After this, normally you can simply use:

git push
git pull


============================================================
BRANCH WORKFLOW — CREATE, WORK, PUSH AND MERGE
============================================================


IMPORTANT:
Always update main BEFORE creating a new branch.

git switch main

git pull origin main


Create a new branch AND switch to it:

git switch -c sub/auxiliary

-c = CREATE a new branch and switch to it.

"sub/auxiliary" is a branch name.
It DOES NOT create a Windows folder.


Check current/all local branches:

git branch

Example:

* sub/auxiliary
  main

* = branch you are currently using.


Create/change your files.

Example:

New-Item -ItemType File -Path ".\secondaryinformation.md"


Check changes:

git status


Stage the specific file:

git add secondaryinformation.md


Commit:

git commit -m "Add secondary information"


Push the new branch to GitHub:

git push -u origin sub/auxiliary


Then on GitHub:

Create Pull Request

sub/auxiliary
      ↓
     main

Review changes
→ Merge Pull Request


After the branch has been merged, return locally to main:

git switch main


Download the merged changes:

git pull origin main


============================================================
SWITCH EXISTING BRANCH vs CREATE NEW BRANCH
============================================================

Switch to an EXISTING branch:

git switch main


Create a NEW branch and switch to it:

git switch -c feature/test-change


So:

-c = CREATE


------------------------------------------------------------
Check branches:
------------------------------------------------------------

git branch


------------------------------------------------------------
Switch back to main:
------------------------------------------------------------

git switch main


============================================================
REBASE
============================================================

If GitHub contains newer commits while you also have local commits:

git pull origin main --rebase


Concept:

GitHub:

A → B

Your local work:

A → C


Rebase tries to produce:

A → B → C'


It first takes the latest GitHub changes and then reapplies your
local changes on top.


If both developers changed incompatible parts of the same file,
Git may stop with a conflict.

Resolve the conflict, then:

git add <resolved-file>

git rebase --continue


If you want to cancel the entire rebase:

git rebase --abort


After successful rebase:

git push


============================================================
FULL FLOW — DOWNLOAD EXISTING GITHUB PROJECT
============================================================

In Android Studio:

VCS
→ Get from Version Control


Repository URL example:

https://github.com/LiteAdGamingStudios/LiteAdLogicgames.git


Choose any desired local folder, for example:

C:\lite_ad_studios\games\litead_logic_games


Click Clone.


Then run:

flutter pub get


If Flutter/Dart is not detected:

Settings
→ Languages & Frameworks
→ Flutter

Flutter SDK example:

C:\Flutter


Then:

Settings
→ Languages & Frameworks
→ Dart

Enable:

Enable Dart support


Dart SDK example:

C:\Flutter\bin\cache\dart-sdk


============================================================
DAILY WORKFLOW
============================================================

Before starting new work:

git switch main

git pull origin main


Create your working branch:

git switch -c feature/my-change


Make changes.


Check:

git status


Stage:

git add .


Commit:

git commit -m "Describe the change"


Push branch:

git push -u origin feature/my-change


Then GitHub:

Pull Request
→ Review
→ Merge into main


Finally update local main:

git switch main

git pull origin main


============================================================
MOST IMPORTANT COMMANDS TO REMEMBER
============================================================

git status
    = What has changed?


git add .
    = Stage all changes


git commit -m "message"
    = Save a Git checkpoint


git push
    = Send commits to GitHub


git pull
    = Get latest changes from GitHub


git restore <file>
    = Discard uncommitted changes


git switch main
    = Switch to existing main branch


git switch -c feature/name
    = Create AND switch to a new branch


git branch
    = Show local branches


git remote -v
    = Show which GitHub repository this project is connected to
```

