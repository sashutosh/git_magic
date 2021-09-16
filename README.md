# git_magic

This file contains git commands which I have found useful for rescuing me from tricky situations and saving hours of work

1. Restore local branch to same as remote, reverting all local changes and commits 

    Context: You have messed up local branch and not sure where you are now. In such situation I have found it best to go back to sanity and restore the remote branch dis-regarding all local commited and un-commited changes


    Template - git reset --hard origin/<branch_name>

    Example - git reset --hard origin/master

2. Quick check what changes a commit contains

    Context: You want to check the history of a branch and the changes that went in a particular commit bit you dont
have only the CLI based tools


    Template - 
    i) git log     //This will show all the recent commits
    
    ii) git show <commit-id> // This will show a diff of the files in the commit


4. Create a branch from a given tag
    
    Context - Your main branch is tagged with release_id and you want to give a patch on a given release

    
    Template
    git checkout -b <new_branch_name> tags/<tag_name>    
    
 5. Get a patch for a commit to apply in another branch.
      Context - You made committed changes in a shared branch. There are other changes on top of it. You want to cherry pick your commit and have it exported as a patch file so that you can mail it to your friend and apply it in his branch.
      git log // Fetch the sha of the commit from history
      
      git format-patch -1 <sha> //Will create a pathc file in the current directory
    
      git am < file.patch

