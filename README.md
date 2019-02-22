# CLI Essentials: Working with Files and Directories in Bash

## Learning Goals

* Demonstrate interacting with files and directories in the command line

## Introduction

Learning command line tools for managing the file system in Bash can give you
more speed and control over your workflow. It's actually designed for us to be
lazy, so let's let the computer to do all the work for us. Some tasks are best
suited to a GUI like word processing, but at the same time, some tasks are more
suited to the command line, data manipulation (reporting) and file management.
The command line will simply become another tool you can add to your belt.
We'll discuss how to perform file management tasks in this lesson.

## Demonstrate Interacting with Files and Directories in the Command Line

With a basic idea of basic `bash` commands, we can start to play around. We'll
show you how to make files and directories and interact with them further. 

### Use `ls` to List Files in Shell

To start, let's show our files and folders. In a new terminal, try this:

```bash
$ ls
```

The command `ls` stands for "**l**i**s**t", so you should see a list of all the
folder and file names in the current working directory. If you pass a directory
name with the `ls` command, you can view all the files and folders in that
directory. 

### Recognize the Use of Flags With Commands

We can use flags on most commands to give more specific instructions or to
change the way the feedback is presented. Most programs also accept flags, or
options for execution. A flag is denotated by a `-` ("dash").  A common flag
that nearly all programs and commands accept is a standalone `h`, for
"**h**elp".

```bash
$ ls -h
```
**Note:** *In some programs, options are passed directly to the command and not via flags.*

Single-character options can typically be combined with each other. For example,
in the `ls` command, `h` is a suffix on the `l` flag meaning "**h**uman readable
formats." They can be combined with `a` meaning "**a**ll information including.
Try these three together:

try `ls -l` try `ls -h` try `ls -lh` (whoa...c-c-c-c-c-combo!)

Combining flags is only valid for single-letter options. A "long option" such
as* `--force` *is defined with more than one character and must be entered with
its own flag.* For example `--force --remote` `--forceremote` or
`--remoteforce`.

### Create Empty Files With `touch`

There are various ways to then create files using the command line, one of the
most common is using the `touch` command to create empty files in the current
directory.

Try this command:

```bash
$ touch hello_world.rb
```

Now try:

```bash
$ ls
```

You should see the file you just created, `hello_world.rb`, in the working
directory. Note that this is an empty file and has nothing inside of it, because
you just created it. 

**Unix systems are _case sensitive_**! This is very important. Other systems
such as Windows are case insensitive when it comes to referring to files. Unix
systems is not like this. As such it is possible to have two or more files and
directories with the same name but letters of different case.

```bash
hello_world.rb
HELLO_WORLD.rb
hello_world.RB
```

In the code snippet above, these are all distinct and separate files.

### Making New Directories Using `mkdir`

Make directories with the command `mkdir`. We can make directories with the
`mkdir` command:

```bash
$ mkdir name_of_directory
```

Now if you enter `ls` you should see the empty directory you just created in the
working directory.

We can make a folder _and_ its parents if they do not exist already by using the
`-p` option. The command `mkdir -p first_directory/next_directory/my_directory`
would also create the first and next folder.

### Use `mv` to Move or Rename Files and Directories

Move, or `mv` is a command that moves one or more files or directories from one
place to another.  Alternatively, think of it as a copy, followed by a delete of
the original. To move a file from the current directory to another location,
enter a path as the third word on the command line.

```bash
$ mv filename /dir1/
```

We can also rename file or directory using the `mv` command. To rename a file
with `mv`, the third word on the command line must end in the new filename.

```bash
$ mv original_program.rb renamed_program.rb
```

### Use `cp` to Copy Files and Directories

The `cp` command stands for "copy" and copies files and folders, just as
expected. This command is used to copy files or group of files or directory. It
creates an exact image of a file on a disk with different file name. This
command require at least two filenames in its arguments. The flag -r recursively
copies subfolders and files.

Try copying the file we just created:

```bash
$ cp hello_world.rb hello_world_again.rb
```

* If the command contains *two* file names, then it copy the contents of 1st
  file to the 2nd file. If the 2nd file doesn’t exist, then first it creates one
  and content is copied to it. But if it existed then it is simply overwritten
  without any warning. So be careful when you choose destination file name.

* If the command has one or more arguments, specifying file names and following
  those arguments, an argument specifying directory name then this command
  copies each source file to the destination directory with the same name. It
  will create the directory if it doesn't exist, but **if it exists then it will
  be overwritten**, so be careful!

```bash
$ cp hello_world.rb hello_world_again.rb name_of_directory
```
Now you have too many files, or some of them are no longer needed. Let's talk
about how to remove files.

### Removing Files With `rm`

To delete a file, we can enter `rm` at a shell prompt. This command stands for
**r**e**m**ove.

```bash
$ rm hello_world.rb
```
**Note:** Deleting a file with rm is *permanent*. This action cannot be undone.

There additional options to `rm`:

* -i (interactive) — Prompts you to confirm the deletion. This option can stop
  you from deleting a file by mistake.
* -f (force) — Overrides interactive mode and removes the file(s) without
  prompting. Use this with caution. This action cannot be undone!
* -v (verbose) — Shows the progress of the files as they are being removed.
* -r (recursive) — Deletes a directory and all files and subdirectories it
  contains.
* Combining the flags `-rf` will do a recursive force delete.

You can also delete directories using `rm` or `rmdir`. If you want to remove all
folders and files in a directory the dull command is `rm -rf name_of_directory`.

**Note:** When using `rm -rf`, be _very_ careful. If you submit a command like
`rm -rf /` , if you will delete the root directory!

## Conclusion

With these commands, we can begin to organize our file system in a manageable
way. We illustrated how to create, move, rename, copy, and delete files and
directories as well as how to avoid causing some chaos with the naming and
removing of files and directories. Most commands also have many useful flags
that can give us additional controls and options. As we get accustomed to
navigating and manipulating file structures in the command line, we will start
to grasp the power of `bash`.

## Resources

- [Top 10 Bash file system commands you can’t live without](https://medium.com/the-code-review/top-10-bash-file-system-commands-you-cant-live-without-4cd937bd7df1)
- [File Manipulation!](https://ryanstutorials.net/linuxtutorial/filemanipulation.php)
- [More About Files!](https://ryanstutorials.net/linuxtutorial/aboutfiles.php)
- [cp command in Linux with examples](https://www.geeksforgeeks.org/cp-command-linux-examples/)