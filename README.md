# Soal_Assignment
# Assignment_2

##Your first challenge is to print "hello world" on the terminal in a single command.

Hint: There are many ways to print text on the command line, one way is with the 'echo' command. Try it below and good luck!
 
Ans: echo " hello world "
Output: hello world
##Print the current working directory.

Ans: pwd
Output: /var/challenges/current_working_directory

##List names of all the files in the current directory, one file per line.

Ans: ls
Output: 01-take.txt
02-the.txt
03-command.txt
04-challenge.txt

##There is a file named access.log in the current directory. Print the contents.

Ans: cat access.log 
Output: 163.56.115.58 - - [09/Jan/2017:22:29:57 +0100] "GET /posts/2/display HTTP/1.0" 200 3240
75.113.188.234 - - [09/Jan/2017:22:30:43 +0100] "GET /posts/foo?appID=xxxx HTTP/1.0" 200 1116
69.16.40.148 - - [09/Jan/2017:22:34:33 +0100] "GET /pages/create HTTP/1.0" 500 3471
225.219.54.140 - - [09/Jan/2017:22:35:30 +0100] "GET /posts/foo?appID=xxxx HTTP/1.0" 500 2477
207.243.19.2 - - [09/Jan/2017:22:38:03 +0100] "GET /bar/create HTTP/1.0" 200 1116
199.37.62.156 - - [09/Jan/2017:22:42:18 +0100] "GET /posts/1/display HTTP/1.0" 200 2477
55.74.240.123 - - [09/Jan/2017:22:44:25 +0100] "POST /posts/1/display HTTP/1.0" 200 3471
251.111.109.143 - - [09/Jan/2017:22:49:02 +0100] "GET /posts/foo?appID=xxxx HTTP/1.0" 200 2477
101.163.230.250 - - [09/Jan/2017:22:52:31 +0100] "DELETE /posts/2/display HTTP/1.0" 404 2477
200.19.168.148 - - [09/Jan/2017:22:57:11 +0100] "GET /posts/foo?appID=xxxx HTTP/1.0" 200 3471

##Print the last 5 lines of "access.log".

Ans: tail -n 5 access.log
Output: 199.37.62.156 - - [09/Jan/2017:22:42:18 +0100] "GET /posts/1/display HTTP/1.0" 200 2477
55.74.240.123 - - [09/Jan/2017:22:44:25 +0100] "POST /posts/1/display HTTP/1.0" 200 3471
251.111.109.143 - - [09/Jan/2017:22:49:02 +0100] "GET /posts/foo?appID=xxxx HTTP/1.0" 200 2477
101.163.230.250 - - [09/Jan/2017:22:52:31 +0100] "DELETE /posts/2/display HTTP/1.0" 404 2477
200.19.168.148 - - [09/Jan/2017:22:57:11 +0100] "GET /posts/foo?appID=xxxx HTTP/1.0" 200 3471


##Create an empty file named take-the-command-challenge in the current working directory.

Ans: touch take-the-command-challenge 

##Create a directory named tmp/files in the current working directory

Ans: mkdir tmp && cd tmp && mkdir files

##Copy the file named take-the-command-challenge to the directory tmp/files

Ans: cp take-the-command-challenge tmp/files/ 

##Move the file named take-the-command-challenge to the directory tmp/files

Ans : mv take-the-command-challenge tmp/files/ 

##A symbolic link is a type of file that is a reference to another file.

  Create a symbolic link named take-the-command-challenge that points to the file tmp/files/take-the-command-challenge.

Ans: ln -s tmp/files/take-the-command-challenge take-the-command-challenge

##Delete all of the files in this challenge directory including all subdirectories and their contents.

Ans: find . -delete

##There are files in this challenge with different file extensions. Remove all files with the .doc extension recursively in the current working directory.

Ans: find . -name "*.doc" -delete
 
##There is a file named access.log in the current working directory. Print all lines in this file that contains the string "GET".

Ans: grep 'GET' ./access.log

##Print all files in the current directory, one per line (not the path, just the filename) that contain the string "500".

Ans : grep -ls 500 *

##Print the relative file paths, one path per line for all filenames that start with "access.log" in the current directory.

Ans : ls

##Print all matching lines (without the filename or the file path) in all files under the current directory that start with "access.log" that contain the string "500". Note that there are no files named access.log in the current directory, you will need to search recursively.

Ans: grep -r -h "500"

##Extract all IP addresses from files that start with “access.log” printing one IP address per line.

Ans: grep -ro ^[0-9.]*

##Count the number of files in the current working directory. Print the number of files as a single integer.

Ans: ls -l | wc -l

##Print the contents of access.log sorted.
Ans: sort access.log

##Print the number of lines in access.log that contain the string “GET”.
Ans: grep -c GET access.log

##The file split-me.txt contains a list of numbers separated by a ; character. Split the numbers on the ; character, one number per line.
Ans: tr ';' '\n' < split-me.txt

##Print the numbers 1 to 100 separated by spaces.
Ans: echo {1..100}

##This challenge has text files (with a .txt extension) that contain the phrase “challenges are difficult”. Delete this phrase recursively from all text files. Note that some files are in subdirectories so you will need to search for them.
Ans: sed -i 'challenge are difficult/d' **/*.txt

##The file sum-me.txt has a list of numbers, one per line. Print the sum of these numbers.
Ans: cat sum-me.txt | xargs | sed -e 's/\ /+/g' | bc 

##Print all files in the current directory recursively without the leading directory path.
Ans: find . -type f -printf "%f\n"

##Rename all files removing the extension from them in the current directory recursively.
Ans: find `pwd` -type f -exec bash -c 'mv "$1" "${1%.*}"' - '{}' \;

##The files in this challenge contain spaces. List all of the files (filenames only) in the current directory but replace all spaces with a '.' character.
Ans: ls | tr ' ' '.'

##In this challenge there are some directories containing files with different extensions. Print all directories, one per line without duplicates that contain one or more files with a ".tf" extension.
Ans: dirname **/*.tf | uniq

##There are a mix of files in this directory that start with letters and numbers. Print the filenames (just the filenames) of all files that start with a number recursively in the current directory.
Ans: find -type f -printf "%f\n" | grep ^[0-9]

##Print the 25th line of the file faces.txt
Ans: head -25 faces.txt | tail -1

##Print the lines of the file reverse-me.txt in this directory in reverse line order so that the last line is printed first and the first line is printed last.
Ans: tac *

##Print the file faces.txt, but only print the first instance of each duplicate line, even if the duplicates don't appear next to each other. Note that order matters so don't sort the lines before removing duplicates.
Ans: awk '!seen[$0]++' faces.txt

##The file random-numbers.txt contains a list of 100 random integers. Print the number of unique prime numbers contained in the file.
Ans: cat random-numbers.txt | sort |uniq | factor | awk 'NF==2'| wc -l


##access.log.1 and access.log.2 are http server logs. Print the IP addresses common to both files, one per line.
Ans: awk 's[$1]++{print $1}' a*

##Print all matching lines (without the filename or the file path) in all files under the current directory that start with “access.log”, where the next line contains the string “404”.
ans: awk ‘/404/{print x}{x=$0}’ **/a*

##Print all files with a .bin extension in the current directory that are different than the file named base.bin.
Ans: for f in t*; do cmp -s bas* $f || echo $f; done

##There are files in this challenge with different file extensions. Remove all files without the .txt and .exe extensions recursively in the current working directory.
Ans: find -type f ! -regex '.*\(exe\|txt\)$' -delete
##How many lines contain tab characters in the file named file-with-tabs.txt in the current directory.
Ans: grep -P "\t" * | wc -l

##There are files in this challenge with different file extensions. Remove all files without the .txt and .exe extensions recursively in the current working directory.
Ans: find -type f ! -regex '.*\(exe\|txt\)$' -delete

##There are some files in this directory that start with a dash in the filename. Remove those files.
Ans: rm ./-*

##There are two files in this directory, ps-ef1 and ps-ef2. Print the contents of both files sorted by PID and delete repeated lines.
Ans: cat ps* | sort -u

##In the current directory there is a file called netstat.out. Print all the IPv4 listening ports sorted from the higher to lower.
Ans: grep 'LISTEN' netstat.out | awk '{print $4}' | grep '\.' | cut -d : -f 2

