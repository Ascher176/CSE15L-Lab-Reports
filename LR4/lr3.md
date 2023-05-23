# Lab report 3
## find  
Source: [https://man7.org/linux/man-pages/man1/find.1.html](https://man7.org/linux/man-pages/man1/find.1.html)  

### size
[-size](https://man7.org/linux/man-pages/man1/find.1.html#:~:text=include%20symbolic%20links.-,%2Dsize,-n%5BcwbkMG%5D%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20File) allows us to search files based on their size. This can be useful for various tasks e.g. finding the smallest/biggest file. It takes units of space (n) as a parameter. To find files that are bigger than n we can add "+" in front of the parameter, for files that are smaller - "-", and nothing for files that take exactly n units of space. By default units of space are 512-byte blocks, but we can use other units by adding a suffixes.  
1. In this example I used a suffix "k" for kibibytes (KiB, units of 1024 bytes), so this command outputs files in technical/ that are bigger than 200 KiB.  
```
[cs15lsp23lt@ieng6-201]:technical:235$ find -size +200k
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-3.txt
./government/About_LSC/commission_report.txt
./government/Env_Prot_Agen/bill.txt
./government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./government/Gen_Account_Office/d01591sp.txt
```
2. In this example I used a suffix "c" for for bytes, so this command outputs files in technical/ that are smaller than 1000 bytes.
```
[cs15lsp23lt@ieng6-201]:technical:242$ find -size -1000c
./plos/pmed.0020191.txt
./plos/pmed.0020226.txt
```  

### type  
[-type](https://man7.org/linux/man-pages/man1/find.1.html#:~:text=true%20%20Always%20true.-,%2Dtype%20c,-File%20is%20of) allows us to search files based on their type. This can be useful for filtering through files to find the ones of certain type.

1. In this example "d" is for directories so the command outputs all the directories in _techical/_ (+ _technical/_ itself as a ".").
```
[cs15lsp23lt@ieng6-201]:technical:243$ find -type d
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
2. In this example "f" is for regular files. (I used this command on a small directory within _technical/_ instead of just _technical/_ so that the command does not output all ".txt" files but only a small portion contained in _government/Alcohol_Problems/_ for the sake of space in this report.)
```
[cs15lsp23lt@ieng6-201]:technical:245$ find government/Alcohol_Problems/  -type f       
government/Alcohol_Problems/DraftRecom-PDF.txt
government/Alcohol_Problems/Session2-PDF.txt
government/Alcohol_Problems/Session3-PDF.txt
government/Alcohol_Problems/Session4-PDF.txt
```  

### delete 
[-delete](https://man7.org/linux/man-pages/man1/find.1.html#:~:text=pattern.%0A%0A%20%20%20ACTIONS-,%2Ddelete,-Delete%20files%20or) allows us to delete files/directories. It is useful for keeping everything organized by deleting files/directories which are no loger needed.  
1. In this example I deleted one of the files in the _911report/_ directory. I used _find_ command again to show that the file is gone.
```
[cs15lsp23lt@ieng6-201]:technical:246$ find 911report/chapter-1.txt        
911report/chapter-1.txt
[cs15lsp23lt@ieng6-201]:technical:247$ find 911report/chapter-1.txt -delete
[cs15lsp23lt@ieng6-201]:technical:248$ find 911report/chapter-1.txt
find: '911report/chapter-1.txt': No such file or directory
```  
2. In this example I deleted the whole _plos/_ directory. I used _ls_ command to show that the directory is gone.
```
[cs15lsp23lt@ieng6-201]:technical:250$ ls 
911report  biomed  government  plos
[cs15lsp23lt@ieng6-201]:technical:251$ find plos/ -delete
[cs15lsp23lt@ieng6-201]:technical:252$ ls
911report  biomed  government
```  

### mmin  
[-mmin](https://man7.org/linux/man-pages/man1/find.1.html#:~:text=link%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20is%20broken.-,%2Dmmin,-n%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20File%27s%20data) allows us to search files/directories based on the time they were last modified. This can be useful for various tasks e.g. seeing if someone was working on files/directories and which ones were changed in particular. It takes minutes (m) as a parameter. To find files that were modified more than m minutes ago we can add "+" in front of the parameter, for files that were modified less than m minutes ago - "-", and nothing for files that were modified exactly m minutes ago.    
1. In this example the commands outputs files/directories that 
