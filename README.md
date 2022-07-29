<div align="center">
  <h1>Git Lean Guide</h1>
  <h3>Lean but practical guide to every day Git commands</h3>
  
  <p>
    <a name="stars"><img src="https://img.shields.io/github/stars/sadanandpai/git-lean-guide?style=for-the-badge"></a>
    <a name="forks"><img src="https://img.shields.io/github/forks/sadanandpai/git-lean-guide?logoColor=green&style=for-the-badge"></a>
    <a name="license"><img src="https://img.shields.io/github/license/sadanandpai/git-lean-guide?style=for-the-badge"></a>
  </p>
  
  <img width="654" alt="image" src="https://user-images.githubusercontent.com/12962887/170864903-b331fc72-71f6-429b-81d4-b5cceb9d4b9f.png" />
  
  <h4>Solutions to 80% of your daily git challenges</h4>
</div>

<br>

---

<br>

### 1. I want to clone a project and start going through the code

- Get the repo url/link
- Open your terminal
- Navigate to the location in the terminal where you want your project to be cloned
- Enter the command `git clone url`

<img width="905" alt="repo clone" src="https://user-images.githubusercontent.com/12962887/170861577-d7111658-96df-4b43-918b-2e2ab3395efd.png">
<br>
<br>

---

<br>

### 2. I have cloned the repo. But I am not able to see the proper code!!!

By default the main/master branch is active. Ask which branch has the relevant code

- Navigate inside the cloned folder `cd repo<-name>`
- Enter the command `git checkout <branch-name>`

<img width="619" alt="checkout" src="https://user-images.githubusercontent.com/12962887/180643741-f3f3fd37-a8d0-459e-b261-4fb4303f80d0.png">

---

<br>

### 3. Someone has made few changes in the code and asked me to pull those changes. What should I do?

- Enter the command `git pull`

<img width="587" alt="pull" src="https://user-images.githubusercontent.com/12962887/173235993-7f2ba191-d9bb-4a78-aec3-35f326e46325.png">
<br>
<br>

---

<br>

### 4. I have modified the code and added changes. How to commit my changes

First stage all the files and then commit your changes. You can create multiple commits.

- Enter the command `git add *`
- Commit the changes `git commit -m 'You commit message'`

<img width="608" alt="commit" src="https://user-images.githubusercontent.com/12962887/180645381-c77af0e5-6d4c-4991-84d7-1572636e34a3.png">
<br>
<br>

---

<br>

### 5. What if I want only some of files added and pushed instead of all the changes?

You can add files by mentioning the file/files with relative or fulll path. You can add file one by one or multiple files at a time using the commands

- Add single file `git add <file-name>`
- Add multiple files `git add <file1-name> <file2-name>`

<img width="619" alt="add" src="https://user-images.githubusercontent.com/12962887/180643543-7ca529df-5126-4a73-9dd1-703af2f03fba.png">

Similarly, to unstage a file use the command `git reset <file>`
<br>
<br>

---

<br>

### 6. I have modified/formatted some code while going through. Now I want the code to be back to the state as it was.

- To reset all the changes `git reset --hard`
- To reset a single file `git checkout HEAD -- <file-name>`

<img width="719" alt="reset" src="https://user-images.githubusercontent.com/12962887/180649258-1dddabf1-bdc2-4706-a537-26eaad4ba99e.png">
<br>
<br>

---

<br>

### 7. I have committed my changes. How can I undo my change?

You can undo the commit resetting the HEAD. If you just want to undo the commit but let the changes be present then use `soft` attribute else if you do want the commit along with the changes then use `hard` attribute

- `git reset --soft HEAD~1` (undo with changes preserved)
- `git reset --hard HEAD~1` (undo with changes removed)

<br>
<br>

---

<br>

### 8. I have made some changes in the branch. Also I wanted to pull the new changes. But it is not working.

The command `git pull` may not work if the changes are done by someone else to the same files by to which you have also modified.

- Stash the canges `git stash save '<name of the change> -u`
- Pull the changes now `git pull`
- Retrieve the changes `git stash apply <n>`

where n is the stash number. To get the list of stashes `git stash list`

<img width="918" alt="stash" src="https://user-images.githubusercontent.com/12962887/181293105-77ec0867-0d95-4f44-99e4-0b1003a6310b.png">

Note: You can stash multiple changes and bring them back as and when you like to

<br>
<br>

---

<br>

### 9. After applying the stash, I am getting a lot of conflicts in the code.

If there are changes in the code on the region of the stashed code, it is expected to get the conflicts. You will have manually resolve and the conflicts carefully.

<img width="596" alt="stash conflicts" src="https://user-images.githubusercontent.com/12962887/180613095-a8e08426-1d15-4a31-956b-55bfdfbdb84d.png">

Below is the view of the VSCode, which helps in easily resolving the conflicts.
![VSCode conflict](https://user-images.githubusercontent.com/12962887/180612978-fffd4307-0045-4fd3-b52c-394d1d9a0059.png)
<br>
<br>

---

<br>

### 10. I have made some code changes. But I want to commit to a new separate branch.

You can create a separate branch out of the current branch and commit it. This works both if you have already made changes or yet to start making changes.

- Create a new branch `git checkout -b <my-branch-name>`
- Stage all the changes `git add *`
- Commit the changes `git commit -m "<some commit message>"`

To switch between the branches use the command `git checkout <original-branch-name>`

<img width="555" alt="branch out" src="https://user-images.githubusercontent.com/12962887/173236172-30ccb855-0b2c-47ae-a711-152f20bc3b67.png">

Note: `my-branch-name` is your local branch and not available for anyone else unless you push it
<br>
<br>

---

<br>

### 11. I just committed but forgot to add few files to the commit. Is there a to update the same commit with some modifications?

Yes. You can update the commit by amending your changes.

- To add files `git add <file-name> <file-name> ...`
- To update the commit `git commit --amend --no-edit`

To update with new commit message `git commit --amend -m 'My new commit message'` (This command can also be used to simply update the previous commit message without any code modifications)

`--no-edit` is used to avoid the prompt to edit the commit message. If you want to modify the commit message as well during the update of the commit, then do not include `-m` along with your commit message

<img width="587" alt="amend" src="https://user-images.githubusercontent.com/12962887/180615625-baa2b6f5-2ca5-454a-bfbf-d7115537cdbf.png">

Note: The `amend` updates the previous commit without creating new one on top of previous. (in reality, Git discards the previous commit and replaces it with new commit)
<br>
<br>

---

<br>

### 12. I am asked to raise a PR to a branch. What am I supposed to do?

You can follow the same steps as given in the previous question. Once done you will push the code and raise a PR. Its that simple. Here we assume you are on 'develop' branch and raising PR to 'main' branch.

- Enter the command `git checkout -b <my-branch-name>`
- Stage all the changes `git add *`
- Commit the changes `git commit -m "<some commit message>"`
- Push the chages `git push` (as the branch is not present on the remote, it will show the command to use)
- Enter `git push --set-upstream origin <my-branch-name>`

<img width="872" alt="" src="https://user-images.githubusercontent.com/12962887/180644568-b2fc1d78-399c-443d-b714-3ab1cafb83bd.png">

The URL to raise the PR will be automatically available as shown above. Use the link and open in the browser.

![image](https://user-images.githubusercontent.com/12962887/180644608-ad9175df-64cd-4f8e-930c-64333ea2222a.png)

Now select the base branch to which you want to raise a PR and click on 'Create a PR'

<br>
<br>

---

<br>

### 13. I do not want a branch anymore. How can I delete the branch?

To delete a branch in locally, checkout out a different branch than the one you want to delete. Here we will delete the branch named 'develop'

- Switch to other branch `git checkout <other-branch>`
- Delete branch `git branch -d <branch-name>`

To delete the branch from remote as well

- Delete remote branch `git push -d <remote> <branch-name>`

<img width="808" alt="image" src="https://user-images.githubusercontent.com/12962887/181604592-a08d6cd4-105e-460b-b694-558f4fcf9680.png">

Note: If `-d` does not allow to delete a branch, use the `d`. Example: `git branch -D <branch-name>`

<br>
<br>

---

<br>

### 14. I want to rename my local and remote branch. How can I do it?

To rename a branch, checkout to the branch and rename it.

- Checkout other branch `git checkout <your-branch-name>`
- Rename your branch `git branch -m <new-branch-name>`
- Push to remote `git push <remote> :<your-branch> <new-branch-name>`
- Set upstream `git push <remote> -u <new-branch-name>`

&lt;remote&gt; is usually origin

<img width="752" alt="image" src="https://user-images.githubusercontent.com/12962887/181599454-22970ea6-8ee4-424c-acfb-5c0c17179c4a.png">

<br>
<br>

---

<br>

### 15. I have made some changes to the code on the branch on which all of the developers are working. How can my make my changes published directly without a PR?

To move the changes from your local machine to online (called origin), follow below steps in your terminal

- Add the changed files `git add *`
- Commit the changes `git commit -m "<some commit message>"`
- Push the changes `git push`

<img width="828" alt="image" src="https://user-images.githubusercontent.com/12962887/170865776-dea5f82e-6ae6-4f60-b70a-0fc8d37fd741.png">
<br>
<br>

---

<br>

### 16. I created a commit and also pushed it. Is it possible to update that commit now?

Yes. You can update the commit even after it is pushed. Everything will follow as mentioned in the previous question, but you will have to force push.

- `git add <file-name> <file-name> ...`
- `git commit --amend --no-edit` or `git commit --amend`
- `git push -f` or `git push --force`

<img width="783" alt="image" src="https://user-images.githubusercontent.com/12962887/180615816-743abb81-765c-4723-b44f-faf00da3a820.png">

Note: You need to be very careful while pushing forcefully, as it may eliminate other commits if someone has done in between. Make sure you are working on the branch and no one else is similutaneous working on the same or branching out from the branch at your commit.
<br>
<br>

---

<br>

### 17. I have created single/multiple commits. When I am trying to push my changes, getting a rejected message. I am stuck!!!

The rejection could be because the remote branch might be ahead of the local branch. Different techniques can be used here to achieve sync.

- Pull the changes `git pull`
- Continue with the merge commit created automatically
- `git push`

![image](https://user-images.githubusercontent.com/12962887/180632103-bc118a25-eb58-4032-bc12-128b2c506e0c.png)

If there are conflicts, then resolve them manually to proceed ahead as shown below.

<br>
<br>

---

<br>

### 18. I followed the above steps, but getting conflicts after git pull.

If there are code changes on the smae region from multiple commits, the conflicts will occur. You need resolve all the conflicts and proceed.

- Resolve all the conflicts
- `git add <file-path>`
- `git merge --continue`
- `git push`

![pull conflict](https://user-images.githubusercontent.com/12962887/180636539-cad6c7ae-ec56-41e0-9ff0-21dd5e95382f.png)

Note: If something goes wrong, in any of the above steps, then there is nothing to panic. Just run `git merge --abort` and redo the steps.

<br>
<br>

---

<br>

### 19. I have created single/multiple commits. When I am trying to push my changes, getting a rejected message. Can I pull the new changes without merge commit (Rebase)?

Yes. You can pull the changes without a merge. This is called as **Rebase**. I know you have heard it a lot. It is very simple though.

- `git pull --rebase`
- After success, `git push`

<img width="982" alt="rebase" src="https://user-images.githubusercontent.com/12962887/181307242-3b2ff96a-1896-43b2-814c-e22cfbc50320.png">

If you get conflicts, then solve all the conflicts. Then

- `git rebase --continue`
- After success, `git push`

![image](https://user-images.githubusercontent.com/12962887/181306723-5d1929bf-2d7f-4648-bb2e-534f26ae4a34.png)

Note: If something goes wrong, in any of the above steps, then there is nothing to panic. Just run `git rebase --abort` and redo the steps.

<br>
<br>

---

<br>

### 20. I have raised a PR. But it is showing conflicts.

![PR conflict](https://user-images.githubusercontent.com/12962887/181507186-92a6c427-553c-4c1e-b87a-0394d23a1bad.png)

PR will show conflicts if the new changes added to the source branch is conflicting with your changes or your branch is lagging. You can either **merge** the changes to your branch or **rebase** your branch. **Follow any of them.**

Assuming that your branch is `develop` and source branch is `main`

#### Merge approach

- Checkout to main branch `git checkout main`
- Pull changes `git pull`
- Checkout to your branch `git checkout develop`
- Merge the changes `git merge main`
- Resolve all the conflicts and add to staging `git add <files>`
- If conflicts are present `git merge --continue`
- Push the changes `git push`

![merge](https://user-images.githubusercontent.com/12962887/181508483-a0b79ea8-431f-499f-b802-522b2e9fd02f.png)

#### Rebase approach

- Checkout to main branch `git checkout main`
- Pull changes `git pull`
- Checkout to your branch `git checkout develop`
- Rebase the branch `git rebase main`
- Resolve all the conflicts and add to staging `git add <files>`
- Run `git rebase --continue` after resolving the conflicts
- Push the changes `git push -f`

![rebase](https://user-images.githubusercontent.com/12962887/181511250-658f490b-0bfe-4d17-bae6-485a1c1d1692.png)

Note: You may have to run `git rebase --continue` multiple times if there are multiple conflicts on your multiple commits.

<br>
<br>

---

<br>

### 21. I have many commits. How can I transform them into a single commit (squash)?

Converting multiple commits into one is known as **Squashing**. We will achieve this by rebasing with the help of interactive feature of editor (VSCode). This will be both easier and simple.

- Run `git rebase -i HEAD~<n>` (here n refers to number of commits to squash)
- Mark all the commits as 'Sqaush' except the oldest one
- Click on 'Start rebase'
- Enter the commit message

<img width="654" alt="squash" src="https://user-images.githubusercontent.com/12962887/181516582-3493d359-0e04-4679-9b9b-2c120aa1adf9.png">

![image](https://user-images.githubusercontent.com/12962887/181514663-9e04cc4a-45f3-41b5-9a4b-bde2f6fda1d5.png)

![image](https://user-images.githubusercontent.com/12962887/181516003-21e0a84f-30c5-47ce-9466-f1a68b7dc697.png)

Note: If you had already pushed the commits, then you will have use the command `git push -f` to reflect sqaush on the remote branch as well.

<br>
<br>

---

<br>

### 22. I have many commits. How can I transform them into a single commit (squash) with just commands?

You can use the technique of undo to achieve this easily.

- Undo the number of commit you need to squash `git reset --soft HEAD~<n>`
- Commit them again `git commit -m 'Commit message'`

Note: If you had already pushed the commits, then you will have use the command `git push -f` to reflect sqaush on the remote branch as well.

<br>
<br>

---

<br>

### 23. I am trying to rebase my branch with same or other branch. As I have many commits, I am getting lot of conflicts on every commit rebase.

- You can first squash all commits to one commit (Refer [21](https://github.com/sadanandpai/git-lean-guide/blob/main/README.md#21-i-have-many-commits-how-can-i-transform-them-into-a-single-commit-squash)).

- Once done, rebase the branch and resolve all conflicts in a single go. (Refer [20](https://github.com/sadanandpai/git-lean-guide/blob/main/README.md#rebase-approach))

<br>
<br>

---

<br>

### 24. I have made changes and committed to a branch. I want to copy the same changes to another branch.

To copy the changes of a commit from one branch to another, you can use **cherry pick**. First obtain its commit id of the commit, which you want to copy.

- Checkout the branch `git checkout <destination-branch>`
- Cherry pick the commit `git cherry-pick <commit-id>`

<img width="607" alt="cherry pick" src="https://user-images.githubusercontent.com/12962887/181609051-5ced1192-0372-45f9-97bf-3491ce070fbf.png">

<br>
<br>

---

<br>

### 25. I have tried to cherry-pick as shown in [24](https://github.com/sadanandpai/git-lean-guide/edit/main/README.md#24-i-have-made-changes-and-committed-to-a-branch-i-want-to-copy-the-same-changes-to-another-branch). But I am getting conflicts.

If you get any conflicts, resolve the conflicts first. Once all the conflicts are resolved, they continue the cherry-pick.

- Add resolved files to stage `git add <file-paths>`
- Continue cherry-pick `git cherry-pick --continue`

<img width="719" alt="cherry pick conflict" src="https://user-images.githubusercontent.com/12962887/181591132-b43e8c0c-609b-4a25-9150-58d7e66b2d5e.png">

<br>
<br>

---

<br>

### 26. I have multiple commits which I want to move to a different branch.

To copy a range of commits from one branch to another, you can notedown the older commit id from history and newer commit id.

- Checkout the branch `git checkout <destination-branch>`
- Cherry pick the commit `git cherry-pick <old-commit-id>..<new-commit-id>`

<img width="719" alt="cherry pick multiple" src="https://user-images.githubusercontent.com/12962887/181591920-d5c07c1e-3347-4ec5-8352-b3dd7561e109.png">

<br>
<br>

---

<br>

### 27. I have pushed pushed my changes and got it merged. I want to revert it immediately.

Revert creates a reverse commit where the changes made will reversed and is created as a new commit. To revert a particular commit, first obtain its commit id.

- Revert the commit `git revert <commit-id>`
- Push the commit `git push`

<img width="808" alt="revert" src="https://user-images.githubusercontent.com/12962887/181597059-5d121194-9f29-425a-bcc1-7cb466856187.png">

<br>
<br>

---

<br>

### 28. How do I set the complete codebase of my branch to codebase of a different branch?

To reset a branch to a different branch, you codebase on that branch will become same as other branch. To achieve this, you can user 'reset' command.

- Checkout to the branch `git checkout <your-branch-bame>`
- Reset with the branch name `git reset --hard <source-branch>`

In this case, 'your-branch-name' will match the codebase of 'source-branch'

<img width="588" alt="reset" src="https://user-images.githubusercontent.com/12962887/181597315-05e8bd39-f9af-40f3-a104-8a11b8ffb52b.png">

<br>
<br>

---

<br>

### 29. I want to delete/undo previous commit from my branch which I have already pushed. I am not looking for revert. I just want to delete it really.

Revert will reverse the changes creating a new commit. If you want to remove the previous commit, then you can undo and force push the branch.

- Reset by undo `git reset --hard HEAD~<n>` (n is the number of commits to undo)
- Push the changes `git push -f`

<img width="707" alt="undo" src="https://user-images.githubusercontent.com/12962887/181600183-a5fb2095-d0cc-4c4e-ae68-3f4eea209979.png">

Note: Force push is needed as the history of the branch is changing in this. If the commit is not pushed then it is not needed

<br>
<br>

---

### License

This repository is MIT licensed. [Read more](./LICENSE)
