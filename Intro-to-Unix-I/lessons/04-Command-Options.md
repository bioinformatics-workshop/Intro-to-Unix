# 04 - Command Options

**Presenter:** Brandon Le  
**Estimated Time:** 10-15 minutes

Most commands have optional parameters that can change its behavior and function. In this lesson, we will learn about optional parameters offered by the commands.

The parameters available for each command varies drastically (some have no options while others have 10+ options)

## Examining the *ls* command options

Previously, we saw that the **ls** command will display the content of a directory

```{}
$ ls
```

To display long form information of the contents of a directory, we use the "-l" option

```{}
ls -l
```
To display **all** contents (hidden and visible), we use the "-a" option

```{}
$ ls -a
```

To display **all** contents in long form, we use both the "-a" and "-l" options

```{}
$ ls -a -l
$ ls -al
```

## How do we know what options are available for each command?

There's a built-in utility called **man** that provides a manual for the command along with all the available options.

```{}
$ man ls
```
> This will show a manual of the *ls* command and all the options available to it

```
LS(1)               General Commands Manual                      LS(1)

NAME
     ls – list directory contents

SYNOPSIS
     ls [-@ABCFGHILOPRSTUWabcdefghiklmnopqrstuvwxy1%,] [--color=when] [-D format] [file ...]

DESCRIPTION
     For each operand that names a file of a type other than directory, ls displays its name as well as any requested, associated information.
     For each operand that names a file of type directory, ls displays the names of files contained within that directory, as well as any
     requested, associated information.

     If no operands are given, the contents of the current directory are displayed.  If more than one operand is given, non-directory operands
     are displayed first; directory and non-directory operands are sorted separately and in lexicographical order.

     The following options are available:
```

For many utilities, typing in the name or using the --help option can provide usage information and options. 


```{}
$ cat -h    
cat: illegal option -- h
usage: cat [-belnstuv] [file ...]
```
