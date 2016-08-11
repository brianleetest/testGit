People need to create a git hub account (to push changes below).

People make a directory.
People do a git clone in that directory:
git clone https://github.com/brianleetest/testGit.git

People cd cd testGit/testDir do a git pull.  
People edit the file. 
  testDir/testFile.txt 
  or one of the others in moreFiles as they do one-on-one groups testDir/moreFiles/
  as people organize into groups to avoid a lot of merges.


---tell no one to do any more git pulls, until told and they only edit assigned  testFile.txt ---

One person, <em>group leader person</em>, in the group commits to the file that group is editing.
...git diff
...git add
...git commit -m "My message"
...git push


<em>Leader person</em> also commits several other files in a second separate commit and pushes the files 
...runs a loop <b>in the directory they are editing only</b>  <tt>for i in {1..10}; do cp testCopy.txt tempFile$i.txt; done </tt>
..git add temp*
..git commit -m "Adding temp files"
..git push

Everyone now does a git pull....
... Everyone should have a conflict on testFile.txt
... Read the message.
... Do the commit as instructed.
..... git add
..... git commit -m  "I am committing my change."
git pull

Now each person must fix the conflict by doing an edit the file that has the conflict, testFile.txt
.....Look for the >>>  <<<<  edit file to desired state.
.... Save file
... git add testFile.txt
....git status

At this point each person (none have pushed) should have resolved the conflict. Do a git status to <tt>Your branch and 'origin/master' have diverged</tt> and that a commit and push is still need.
......note that you have other staged files (all the tempFiles).... this is OK
......note this is where if you didn't 'go with the flow' and commit these changes around the tempFiles you would be smashing other changes beyond the merge conflict.  Go ahead and add those files.
...git commit "I am doing a merge resolution around testFile.txt"
...git push

The first to push will be free and clear, each other person in group will have to go through
a second set of  merge conflicts as each new person commits their merge resolutions.


Leader Repair:  To reset, delete all the temp files.
...rm temp* 
Replace so there is just a testFile.txt  and testCopy.txt

