People need to create a git hub account (to push changes below).
The owner of the repository has to go to settings and add the new github accounts as collaborators. 

People make a directory to clone in.
People do a git clone in that directory:
+ git clone https://github.com/brianleetest/testGit.git

People cd cd testGit/testDir do a git pull.  
People edit the file. 
+ vi testDir/testFile.txt 

Or people edit  one of the others in moreFiles as they do one-on-one groups testDir/moreFiles/
  as people organize into groups to avoid a lot of merges.

---No one should do any more git pulls, until told and they only edit assigned  testFile.txt ---

<em>Only a group leader</em>, in the group commits to the file that group is editing.
+ ...git diff
...git add
...git commit -m "My message"
...git push


<em>Leader person</em> also does a second commit of several other files in a second separate commit and pushes the files 
+ ...runs a loop <b>in the directory they are editing only</b>  <tt>for i in {1..10}; do cp testCopy.txt tempFile$i.txt; done </tt>
+ ..git add temp*
..git commit -m "Adding temp files"
..git push

---Once <em>group leader</em> pushes, everyone now does a git pull---
+ ... Everyone should have a conflict on testFile.txt
... Read the message.
... Do the commit as instructed.
..... git add
..... git commit -m  "I am committing my change."
git pull

Now each person must fix the conflict by doing an edit the file that has the conflict, testFile.txt
+ .....Look for the >>>  <<<<  edit file to desired state, it is better if you add some unique info.
.... Save file
... git add testFile.txt
....git status

At this point each person (<b>none have pushed</b>) should have resolved the conflict in the file and can do a git status to see <tt>Your branch and 'origin/master' have diverged</tt> and note that a commit (and push) is still needed.
+ ......note that you have other staged files (all the tempFiles) that you did not add .... this is OK
......but this is where if you didn't 'go with the flow' and commit these other changes seen in the tempFiles you would be smashing other developments beyond your merge conflict.
+ Go ahead and do the commit with all those files staged to go along with your commit.  ...git commit -m "I am doing a merge resolution around testFile.txt"
...git push

The first to push will be free and clear, each other person in group will have to go through
a second set of  merge conflicts as each new person commits their merge resolutions.


Leader Repair:  To reset, delete all the temp files.
...git rm temp* 
Replace so there is just a testFile.txt  and testCopy.txt

