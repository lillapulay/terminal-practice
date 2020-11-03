# Terminal Practice

Present Working Directory

```$ pwd```

Present Working Directory without symlinks

```$ pwd -P```

Make Directory

```$ mkdir```

Clear history

```$ clear```

List files

```$ ls```

List files in a different directory

```$ ls /path/to/dir```

List files with the long file format

```$ ls -l```

List files - Human Readable Sizes

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

Change Directory

```$ cd```

Change directory one folder up

```$ cd ..```

Change to Home Directory using tilde

```$ cd ~``` or ```$ cd``` without any arguments

Remove a file permanently(!)

```$ rm```
