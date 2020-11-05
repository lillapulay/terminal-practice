# Terminal Practice

Present working directory

```$ pwd```

Present working directory without symlinks

```$ pwd -P```

Make Directory

```$ mkdir foo```

Create intermediate directory (nested)

```$ mkdir -p a/b/c```

Verbose output (prints the results of mkdir in the console)

```$ mkdir -v a``` output: ```mkdir: created directory 'a'```

Clear history

```$ clear```

List files

```$ ls```

List files in a different directory

```$ ls /path/to/dir```

List files with the long file format

```$ ls -l```

List files with human readable sizes

```$ ls -h``` or ```$ ls -lh```

List all files, including hidden and invisible files

```$ ls -a```

Sort by size

```$ ls -S``` or ```$ ls -lhS```

Sort by last modified time 

```$ ls -t``` or ```$ ls -lt```

Reverse sort

```$ ls -r``` or in combination with other commands, e.g. ```$ ls -lSr``` (lists smaller files first, etc.)

Hard link (create an identical copy of the linked file on disk, that gets updated automatically as the source file gets updated)

```$ ln a.txt b.txt``` where a.txt is the source file, b.txt is the linked file. If deleting the source file, the target file lives on as an independent file. 

Forcing a link - if the source file already exists

```$ ln -f a.txt b.txt```

Symbolic links - to create a link to a directory (can be used for files as well) - with symlinks the OS creates a new, small file pointing to the target file or directory

```$ ln -s a.txt b.txt```

Create a file

```$ touch```

Change directory

```$ cd /path/to/target```

Change directory one folder up

```$ cd ..```

Change to home directory 

```$ cd ~``` using tilde, or ```$ cd``` without any arguments

Delete a file permanently - supports the same flags and arguments as the ```cp```command

```$ rm -v a.txt``` lists files that were deleted

Delete an empty directory

```$ rmdir foo```

Delete a non-empty directory

```$ rmdir /S foo```

Force delete a non-empty directory without confirmation
```$ rmdir /Q /S foo```

Copying a single file

```$ cp a.txt b.txt``` (source file + target file)
  * the target can either be the name of the file we are copying to
  * or the directory we want to copy to - if only specifying the directory, the original file name of the source file will be used to create a new file in the target directory
  
Copying multiple files

```$ cp a.txt b.txt foo```
  * the last argument must be a directory
  * the original file names of the source files will be used as the names of the new files in the target directory
  * we can pass patterns to it: ```$cp *.txt foo```

Copying + verbose output

```$ cp -v a.txt b.txt```

Copying directories - copying be default expects a file, not a directory, so we need to pass a flag:

```$ cp -Rv foo bar``` copies all files from dir foo to dir bar

Force overwriting a file - e.g. when two files are owned by two different users ('permission denied')

```$ cp -f a.txt b.txt```

Confirm owerwriting a file (when copying multiple files)

```$ cp -i a.txt b.txt``` will prompt for confirmation (y/n)

Moving files - supports the same flags and arguments as the ```cp```command (```mv``` is a combination of ```cp``` and ```rm```)

```$ mv -v a.txt b.txt```
 * doesn't support moving files accross systems, that can be done like:
   1. ```$ cp a.txt b.txt```
   1. ```$ rm a.txt```

Redirecting output - can be used to redirect the output of one command to the input to another command - uses the pipe (|) operator

```$ ls -a ~ | grep _``` pipes the output of the ```ls``` command to the input of the ```grep``` command to find all the files in the home directory that contain an underscore ```(_)```

Chaining commands together - using pipe (|)

```$ ls -a ~ | grep _ | sed "s/_/-/g"``` takes the output of a listing and passes it to the ```sed``` command to change all of the underscores to dashes

Writing to a file - using the output

```$ ls -a ~| grep _ > underscores.txt``` would write the results of our search for files in the home directory that containt underscores

Reading from a file - can be done using the ```<```


Copy-paste: ```ctrl-shift-c``` then ```ctrl-shift-v```
Shortcut to open everything in a project directory: ```.``` or in VS Code: ```code .``` or in a different dir, e.g.: ```code my_awesome_project/.``` by specifying the path

Rename a file

```$ mv folder/old-file.txt folder/new-file.txt```


## GIT

Adds all files

```$ git add -A```

Adds files in the current directory

```$ git add .```

Shows files in the staging area

```$ git status```

Removes a file from the staging area

```$ git reset```

Adds commit message

```$ git commit -m "Message"```

Shows details

```$ git log```


#### Pushing changes

```$ git pull origin master``` First pull any changes made since the last pull (origin: name of the remote repo, master: branch we push to)

```$ git push -u origin master``` Then pushes the changes we made (-u: we want to associate our local branch with the remote branch, so in the future it's enough to use git push and git pull)


#### Merge a branch

```$ git checkout master```

```$ git pull origin master```

```$ git branch --merged``` Checks if a branch is already merged

```$ git merge branchname``` 

```$ git push origin master``` Pushed the changes to master branch on the remote repo


#### Delete a branch

```$ git branch --merged``` Checks which branches are already merged

```$ git branch -d branchname``` Deletes the branch locally

```$ git branch -a``` Lists branches (remote repo)

```$ git push origin --delete branchname``` Deletes the branch in the remote repo



#### Cloning a remote repo

```$ git clone <url> <where to clone>``` - . as destination: clones it into the current directory

```$ git remote -v``` Information about the repository

```$ git branch -a``` Lists all branches of a repo

```$ git branch``` Lists local branches

```$ git diff``` Shows the changes made to the code


#### Common workflow

Creating a new branch

```$ git branch new-branch```

Checking out the newly created branch

```$ git checkout new-branch```
