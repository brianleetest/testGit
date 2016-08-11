People do a git clone:
git clone https://github.com/brianleetest/testGit.git

People do a git pull.  
People edit the file. 
  testDir/testFile.txt  
  or one of the others as they do one-on-one groups testDir/moreFiles/
  organize into groups to avoid a lot of merges
    (Maybe they add a new paragraph before the end).

---tell no one to do any more git pulls, until told and they only edit assigned  testFile.txt ---

One person, group leader, in the group commits a change to the file his/her group is editing.
...git add
...git commit -m "My message"
...git push
...Group can do more edits if they like.

Leader person also commits several other files in a second separate commit, pushes
.. runs a loop
   for i in {1..10}; do cp testCopy.txt tempFile$i.txt ; done
..git add temp*
..git commit -m "Adding temp files"
..git push

Everyone now does a git pull....
... Everyone should have a conflict on testFile.txt
... Read the message.
... Do the commit as instructed.
..... git add
..... git commit -m  "I am committing my change."
Git pull

Fix the conflict now by doing an edit the file that has the conflict, testFile.txt
.....Look for the >>>  <<<<  edit file to desired state.
.... Save file
... Git add the file testFile.txt
....Git commit "I am doing a merge resolution around testFile.txt"
....Git pull
Git status
......note that you have other staged files (all the tempFiles).... this is OK
......note this is where if you didn't 'go with the flow' and commit these changes around the tempFiles you would be smashing other changes beyond the merge conflict.
...git commit
...git push

Each person in group will have to go through these merge conflicts as each new person commits their merge resolutions.


Leader Repair:  To reset, delete all the temp files.
...rm temp* 
Replace so there is just a testFile.txt  and testCopy.txt

