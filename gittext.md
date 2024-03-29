
 reset git 

git config --list
git config --global --unset-all user.name
git config --global --unset-all user.email

git credential-manager uninstall

git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

git config --global --get user.name
git config --global --get user.email

git pull origin main

git branch new-branch

git checkout new-branch



git add .
git commit -m "Change to new Git account"
git push origin <branch-name> 


 ******  Git commands ********

1-  git status

2-  git add -A  (add all files changes)

2-  git add path_of_file ( ex- application/controllers/<controller-file>.php)  -> add paticular files 

3-  git commit -m 'write msg here'

4-  git push origin  branchName  (use for  push your changes)

5-  git checkout . (use to delete your change before commit)

6-  git checkout branchName (go to given branch name)

7-  git branch (To check your current branch) 

8-  git checkout -b branchName (create new branch)

9-  git fetch --all  (to use see all branch on this repo)

10- git pull origin branchName (take pull)

11- git log (see your commit)

12- git clone  link (to clone new repo)

13- git fetch origin (use to fetch branch)




It looks like you're encountering an issue with large files exceeding GitHub's file size limit. GitHub has a file size limit of 100 MB, and the files mentioned in the error message are larger than that.

The error message suggests using Git Large File Storage (LFS) to handle large files. Git LFS is an extension to Git that allows for versioning large files without storing them directly in the Git repository.

Here's what you can do:

1. Install Git LFS on your local machine. You can download it from https://git-lfs.github.com/.

2. Once installed, run the following commands in your repository:

    ```bash
    git lfs install
    ```

3. Track the large files using Git LFS. In your case, it seems that the large files are located in the `.angular/cache` directory. You can use the following command to track these files:

    ```bash
    git lfs track ".angular/cache/**/*.pack"
    ```

   This command tells Git LFS to track all files with the extension `.pack` in the `.angular/cache` directory and its subdirectories.

4. Add, commit, and push the changes:

    ```bash
    git add .
    git commit -m "Add Git LFS tracking for large files"
    git push
    ```

   This will update your repository with the Git LFS tracking information.

5. Make sure that your `.gitignore` file includes the `.gitattributes` file to prevent it from being committed to Git LFS:

    ```
    .gitattributes
    ```

   This ensures that the `.gitattributes` file itself doesn't cause issues with file tracking.

After these steps, Git LFS should handle the large files, and you won't encounter the GitHub file size limit issue. Note that you may need to configure Git LFS on your GitHub repository as well, following the instructions provided by GitHub.


