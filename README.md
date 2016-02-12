# When you start a new feature:

```
  git checkout -b your_branchs_name
```

# To upload your changes on your branch

```
  git add changedfile1.file
  git add changedfile2.file
```

- then

```
  git commit -m 'uploading those changes'
```

- Publish your branch

```
  git push origin your_branchs_name
```

And that's it.

*BUT*

You need to add new changes, or fixes 

- Make the fix

- Add the changed files
```
 git add changed_again.x
```

- Make a new commit 
```
  git commit -m 'silly fix'
```

- Push it
```
 git push origin your_branchs_name
```

* But I don't think other people should see that commit message it's pointless

```
  git rebase -i HEAD~2
```

* this is an interactive rebase it will open your default text editor
* and show you the list of messages ( many as the numbers after the ~)

- it will open a text file as

commithash 'uploading those changes'
commithash 'silly fix'

- so if you add an f or an s before the commit it will flat/squash it 

- after that just push -f your change on your branch and you are ready to go

```
 git push -f origin your_branchs_name
```

* What happens if my branch is behind the master/qa branch?

* Don't merge, do a rebase *

```
 git pull --rebase origin master_or_qa
```

- If there's a conflict you can fix it, add it ( with git add) and do git rebase --continue
- If you don't know how to fix it, git rebase --abort and ask for help
