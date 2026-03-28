#Tryhackme - Linux Foundamentals 01

## What I learned
- How to use Linux terminal
- Basic command for navogation

## Command Used
- echo
- Whoami

  Interacting With the Filesystem
- ls
- cd
- cat
- pwd
  
  Searching
- Find
- Grep

  Shell Operator
- &
- &&
- >
- >>

#What I did 

Interacting With the Filesystem
- echo = Output any text that we provide
- Whoami =  check user
- ls = list file in directory if directory contains a file will show list 
- cd = change current directory to we  cd + path
- cat = read content in file
- pwd = print our current directory path 

 Searching
 - `Find` = if we already know file name we can use find -name filename.text
   `find -name passwords.txt` in case dont know file name we can construct a command such as
   `find -name *.txt`  we can get any name in txt file type with file directory path

- `grep`
  `wc` More I have learn some trip, In the case that I want to know how many line ? error ? in example access.log file we can use command like this  `wc -l access.log`

  Grep Word from file : I want to search word in file , We can use command grep "error" access.log
  Grep word from all file in folder :  `grep -R`   example ` grep -R  "Hello" /etc/  `












