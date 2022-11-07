[Back to Cheatsheets Index](README.md)
# bash Cheatsheet

#### Count number of files in a directory
Counts number of files with .JPG extension in directory and subfolders (recursive).
```
find . -name \*.JPG -not -path \*/\.\* | wc -l
```
