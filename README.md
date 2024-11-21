# git-practice-repo

A repository for KH + KE to practice git features.

## 30-minute speed git tutorial

### Overview
- Git is a tool for keeping track of changes to code.
- It lets multiple people work on the same codebase without impact each other.
- It lets you easily roll back changes to a previous point in time if something breaks.
- It also lets you keep multiple versions of code.

The main git features to know are
- Repository (repo)
  - This is the whole codebase.
- Fork
  - This is when you make your own copy of another codebase.
    - E.g. you can fork the code for [Linux](https://github.com/torvalds/linux) and start building your own operating system based on Linux if you want (but it's more than a one man job!).
  - Once you've forked a repo, it's a separate project that is no longer part of the original -- the original is called the `source` or `upstream` repo.
- Branches
  - These are separate "timelines" of the codebase. They can split off from each other like branches on a tree.
    - As an example, a common structure is to have separate "branches" for:
    - The main `prod` (production) version that is live and public. When you download the game "DOOM" from Steam / their website, the version you're getting is the latest release from their production branch on [their repo](https://github.com/id-Software/DOOM)
    - The `dev` version, usually it's the upcoming release that is being tested but not quite finished
    - `feature` branches, for individual changes (e.g. new items / game modes) that are still being worked on.
- Commits
  - These are the individual "steps" in a timeline.
    - For example if you're adding a new item to a game, some commits might be "Added item icon." "Added item description." "Added item functionality." "Fixed item not appearing in shop." etc.

Other useful git terms:
- Remote
  - This is the online version (e.g. the uploaded copy on GitHub)
- Local
  - The offline version on your PC
- Clone
  - This is when you download a git repo to work on locally.
- Origin
  - The common name for the main remote copy.
  - E.g. if you clone this repo, the origin will be `https://github.com/KaiStarkk/git-practice-repo`
- Push
  - Uploading your local version to the remote
- Pull
  - Downloading and merging in the latest changes from the remote version to your local one
- Merge / rebase
  - Merging is when you combine branches. For example, merging a finished `feature` back into `dev` so it can be tested.
  - Rebase is the same thing except instead of making a new commit that combines the changes, it puts the changes together sequentially one after the other.
  - NOTE:
    - Don't worry about it for now but just be aware that this can get complicated.
    - Usually, git is smart enough for two people to change the same file if they changed different lines of code.
    - If they changed the exact same line of code though, they have to pick one version to keep.
- Pull request
  - When you want the owner of an original repo to import the changes from your fork.

### Tutorial

Try this as a first test to get used to git.
If you get any errors let me know.

1. Download and install git.
   On Windows it should add itself to your environment variables so that you can type ``git --version`` from the command prompt.
2. Fork this repo on GitHub (click fork on the main repo page). This will make a copy in your own account.
3. Go to the web page for your forked version and click this button to copy the url:
   ![image](https://github.com/user-attachments/assets/603946f5-81c6-4927-a5c7-321fb28fcb93)
4. Choose a place to save your code projects. Mine are in `C:\Users\my_username\development\`.
   Open that folder up in explorer and right click. There is an option to open a terminal there:  
   ![image](https://github.com/user-attachments/assets/167a12f0-ccb8-4d29-927e-f3d62faf298e)
6. The terminal should show the current directory in the prompt. Depending on what terminal you use it might look quite different
   ![image](https://github.com/user-attachments/assets/14a63007-88dc-4119-b822-df0b189fcb6b)
7. Now you can clone your fork by typing `git clone URL` where `URL` is the URL you copied earlier.
8. Git should clone the repository into a new subfolder. You can navigate into it with `cd DIRECTORY` where `DIRECTORY` is the name of the project folder it created.

Now you have a local copy of the repo that you can make changes to. Let's continue:

1. It's always recommended to make changes on a dedicated branch. It's good to give branches descriptive names. Make one with `git branch bugfix/remove_readme_bug`
2. Now you can modify the files. Use whatever editor or IDE you prefer. Open the README.md file (this file!) and remove this bug: ✅
3. After saving the file, you've made your changes. You can add the file to the "staging area" with `git add .` (the dot means "everything in the current directory"). The staging area is like a checklist of files you're getting ready to commit.
4. Now you can commit the changes to make a new "step" in the timeline of your branch, with `git commit -m "Fix bug"`. The `-m` means "message", which all commits have to have to describe what was changed. Git might ask you to save your email address and name at this point, just follow the instructions it gives.
5. You can now see that your commit is saved in the branch timeline, with `git log`. It should show your change as the most recent change in the list at the top.
6. Next step is pushing this up to GitHub. You can do this with `git push`

Done! You now have your changes up on GitHub. But they're still living on your forked version at `YOURNAME/git-practice-repo`. To get it incorporated into the original repository, you can create a pull request by going to GitHub in your browser and going to the page for your fork. It should show a button offering to create a new pull request.

Follow the steps in that form to submit a request to me. Once I receive it, I'll accept the pull request, which will update this original source repository and you'll see your changes in `KaiStarkk/git-practice-repo`
