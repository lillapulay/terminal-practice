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

Remove a file permanently(!)

```$ rm```

Copying a single file

```$ cp a.txt b.txt``` (source file + target file)
  * the target can either be the name of the file we are copying to
  * or the directory we want to copy to - if only specifying the directory, the original file name of the source file will be used to create a new file in the target directory
  
Copying multiple files

```$ cp a.txt b.txt foo```
  * the last argument must be a directory
  * the original file names of the source files will be used as the names of the new files in the target directory
  * we can pass patterns to it:
    * ```$cp *.txt foo```
