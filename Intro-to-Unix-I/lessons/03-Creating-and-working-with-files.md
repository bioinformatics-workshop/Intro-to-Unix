# 03 - Creating and Working With Files

**Presenter:** Brandon Le  
**Estimated Time:** 30-40 minutes

In this lesson, we will learn how to create and work with files and directories. 

## Making Directories

To make a directory, we use the **mkdir** command.

```
$ mkdir directory_name
$ mkdir directory1 directory2 directory3 ...
```

A directory within a directory

```
$ mkdir directory_name
$ mkdir directory_name/sub_directory
```
A directory within a directory (using the **-p** option)
```
$ mdkir -p directory_name/sub_directory
```
> **-p** : option to tell the **mkdir** program to create the parent directory (directory_name), if it doesn't already exist.

## Touch to Create Files

Using the **touch** command, you can create an empty file.

```
$ touch file1.txt
$ touch file2.txt file3.txt file4.txt
```

Create a file within a specific directory

```
$ touch directory_name/sub_directory/sub_file1.txt
```

> This will create a file named "sub_file1.txt" within the "sub_directory" that's under the parent directory "directory_name"

## Copying Files (cp)

To make copies of a file, we will use the **cp** command.

The command takes as inputs: (1) the file to copy and (2) where to copy the file.

```
$ cp file1.txt ~/file1.txt
```
> This command will copy the file "file1.txt" to the home directory (~) with the name "file1.txt"

You can copy and change the name of the file

```
cp file1.txt ~/fileA.txt
```
> This command will copy the file "file1.txt" to the home directory (~) with the name "fileA.txt"

To copy an entire directory and all its contents, we use the option (-r) to recursive copy the content

```
$ cp -r directory/sub_directory_A directory/sub_directory_B
```
> This command will copy the entire content of "sub_directory_A" into a new directory call "sub_directory_B"

## Moving and Renaming Files
To move files from one directory to another, we will use the **mv** command.

The mv command takes two inputs: (1) the file you want to move and (2) where you want to move

Suppose I want to move sub_file1.txt from the "sub_directory" to the parent directory "directory_name"

```{}
$ mv directory_name/sub_directory/sub_file1.txt directory/ 
```

The **mv** command can also be used to rename a file

```
mv sub_file1.txt file1.txt
```
> This will change the name of sub_file1.txt to file1.txt


## Looking inside

There are several commands that allows you to examine the contents of a file.

Using **cat** to display the content

```
$ cat file1.txt
$ cat file1.txt file2.txt
```
> The full content of the file(s) will be displayed on the terminal

**cat** can also be used to join (concatenate) files

```{}
$ cat file1.txt file2.txt > file3.txt
```
> This command will combine the contents of files "file1.txt" and "file2.txt" into a new file "file3.txt"



To obtain a quick view of the file (but not edit)
```{}
$ less file1.txt
```
> A buffer of the content will be displayed on the terminal. You can use the arrow key/space bar to move up or down the file. Press "**q**" to quit and exit the buffer.

> Note: After quitting, the contents of the file is no longer on the terminal (it only existed temporarily in the buffer).

```{}
$ head file1.txt
```
> The first 10 lines in the file will be displayed on the screen 

```{}
$ tail file1.txt
```
> The last 10 lines in the file will be displayed on the screen 

## Removing Files and Directories

To remove an empty directory, we can use the **rmdir** command.

```{}
$ rmdir directory_name
```

To remove a file, we can use the **rm** command.

```
$ rm file1.txt
$ rm file1.txt file2.txt
```

>**Critical Note**: Once a file or directory is removed, it's gone forever (there are no trash bins to recover the file or folder). Be extra careful when using this command.