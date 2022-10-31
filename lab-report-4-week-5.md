# Week 3 Lab Report 

## **Command Line options for "find":**

***1: The -type option***
```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find -type d
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

Description:
This command is finding all the directories in the technical direcotry. It is useful to see all the directories and subdirecotries in one screen.

```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical/911report$ find -type f
./chapter-1.txt
./chapter-10.txt
./chapter-11.txt
./chapter-12.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-2.txt
./chapter-3.txt
./chapter-5.txt
./chapter-6.txt
./chapter-7.txt
./chapter-8.txt
./chapter-9.txt
./preface.txt
```

Description:
This command is finding all the files in the technical/911reports direcotry. It is useful to see all the files in that directory

```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find -type d,f > listOfFiles
```
Description:
This command is finding all the directories and files in the technical direcotry and saving that output to listOfFiles. It is useful to see all the files and directories in that directory when you are working on terminal, so you know where to look up certain files or diretories.

***1: The -size option***
```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find -size 10b
./government/Media/Annual_Fee.txt
./government/Media/Barnes_new_job.txt
./government/Media/Library_Lawyers.txt
./government/Media/Lindsays_legacy.txt
./government/Media/Supporting_Legal_Center.txt
./plos/pmed.0020187.txt
./plos/pmed.0020198.txt
./plos/pmed.0020235.txt
./plos/pmed.0020236.txt
./plos/pmed.0020239.txt
./plos/pmed.0020257.txt
```

Description:
This command is finding all files that have a size of 10 bytes rounded up. It makes it easier to find files with a certain number of characters.

```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find -size 1k
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
./plos/pmed.0020191.txt
./plos/pmed.0020226.txt
```

Description:
This command is finding all files that have a size of 1KiB rounded up. It is useful when looking for a file of a certain size.

```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find -size 1M > listOfFiles2
```

Description:
This command is finding all the files that have a size 1 MiB rounded up. It is useful to pass the output into another file so it can used as reference as there a lot of files, and it won't fit in the terminal.

***1: The -mtime option***
```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find -mtime -1
.
./911report
./911report/chapter-1.txt
./listOfFiles
./listOfFiles2
./listOfFiles3
```

Description:
This command is finding all the files and directories that have been modified within a day. It is useful to see which files have been edited in the working directory.

```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find . -type d -mtime -3
.
./911report
```
Description:
This command is finding all the directories that have been modified within the past 3 days. It is useful to see which directories have been edited recently 

```
vmaganti@VrishankMagantisPC:/mnt/c/Users/vrish/Documents/GitHub/docsearch/technical$ find . -type f -mtime +7 > listOfFiles3
```
Description:
This command is finding all the files that have been modified at least 7 days ago. It is useful to see which files have been edited at some certain point. The output is sent to listOfFiles3 so all the file names are there for reference.
