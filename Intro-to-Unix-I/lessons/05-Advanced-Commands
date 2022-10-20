# 05 - Advanced Unix Commands

**Presenter:** Brandon Le  
**Estimated Time:** 30-40 minutes

In this lesson, we will tackle some more advanced Unix tools and commands.

## Redirecting Output (>)

Most command outputs show up on the terminal screen. We can re-direct the output of a command from the screen to a file using the ">" symbol.


```{}
$ ls -l > list.txt
```
> This command will list the contents of a directory in the long form (-l) format but instead of outputing the results to the terminal screen, the results will be stored in the file "list.txt"

## Finding Matches (grep)

The **grep** utility allows you to find pattern matches within a file.


```{}
$ grep
usage: grep [-abcdDEFGHhIiJLlMmnOopqRSsUVvwXxZz] [-A num] [-B num] [-C[num]]
        [-e pattern] [-f file] [--binary-files=value] [--color=when]
        [--context[=num]] [--directories=action] [--label] [--line-buffered]
        [--null] [pattern] [file ...]
```

```{}
$ grep "apple" training_course/brandon/fileA.txt

apples
pineapples
```
> This will search for the occurrence of "apple" within the file "fileA.txt" and reports all lines that contain the pattern.

To find lines that do not contain the pattern "apple", we can use the (-v) option
```{}
$ grep -v "apple" training_course/brandon/fileA.txt
```




## Linking Commands with the Pipe

If you're creating a workflow, there can be a lot of intermediate files generated during the process. To simplify the workflow without the generation of intermediate files, we can use the "**|**" (aka pipe) to link commands. The output from one command will serve as the input for another command.

```{}
$ grep "et" training_course/brandon/fileA.txt | head -5
```
> This command will first search for the pattern "et" within the file "fileA.txt". The results from the grep will feed into the next command. `head -5` will output the first 5 lines from the input

## Getting Wild (with the * wildcard)

The * character acts as a wildcard and can be useful in identify unique patterns

For example, suppose we want to list all home user folders starting with the letter "b", we can do so by:


```{}
$ ls -d training_course/b*

training_course/bob     training_course/brandon
```
> This will list (ls) all the directories (-d) that starts with the letter "b". The * indicates characters after "b" can be anything.


```{}
$ ls -d training_course/*n

training_course/brandon
```
> This command will list all directories that ends with the letter "n"

## Cut up the File

**cut** is a command that allows you to easily select columns of a data file. 

```{}
$ cut -f1-4 file1.txt
```
> This will "cut" fields/columns 1 through 4 from file1.txt

## Sorting Things Out (sort)

The **sort** command allows you to sort the file (in reverse or chronological order, by numbers or dictionaries, etc)

Suppose we have a file containing the following information:

```{}
$ cat training_course/brandon/file1.txt

chr1    10  20  B
chr1    1   5   A
chr2    3   15  C
```

To sort that file by the first column, followed by the second column (in numerical order)
```{}
$ sort -k1,1d -k2,2n training_course/brandon/file1.txt

chr1    1   5   A
chr1    10  20  B
chr2    3   15  C
```

To sort by the second column (numerically) (descending order)
```{}
$ sort -k2,2nr training_course/brandon/file1.txt

chr1    10  20  B
chr2    3   15  C
chr1    1   5   A
```

## What's Unique (uniq)

The **uniq** command will extract unique entries within a file

```{}
$ cat training_course/brandon/file2.txt

chr1    10  20  B
chr2    3   15  C
chr1    1   5   A
chr1    1   5   A
chr1    1   5   A
chr1    1   5   A
```

```{}
$ uniq training_course/brandon/file2.txt

chr1    10  20  B
chr2    3   15  C
chr1    1   5   A
```

## Count them all (wc)

The **wc** command is useful for counting lines, words, characters, within a file

```{}
$ cat training_course/brandon/file2.txt

chr1    10  20  B
chr2    3   15  C
chr1    1   5   A
chr1    1   5   A
chr1    1   5   A
chr1    1   5   A
```

Counting by lines
```{}
$ wc -l training_course/brandon/file2.txt

5 training_course/brandon/file2.txt
```

Counting by words
```{}
$ wc -w training_course/brandon/file2.txt

24 training_course/brandon/file2.txt
```

Counting by characters
```{}
$ wc -m training_course/brandon/file2.txt

107 training_course/brandon/file2.txt
```

Counting by lines, words, and byte
```{}
$ wc training_course/brandon/file2.txt

5      24     107 training_course/brandon/file2.txt
```

## Laying Pipes

We can use a combination of these commands consecutively with the | function to arrive at the final output

```{}
$ cat training_course/brandon/file2.txt

chr1    10  20  B
chr2    3   15  C
chr1    1   5   A
chr1    1   5   A
chr1    1   5   A
chr1    1   5   A
```

```{}
sort -k1,1d -k2,2n training_course/brandon/file2.txt | uniq | wc

3      12      54
```
> This command first sorts the file by columns 1 and 2, then extracts the unique entries and determines the word count of the remaining entries


