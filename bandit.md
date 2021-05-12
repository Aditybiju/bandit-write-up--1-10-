#BANDIT WRITE-UP(1-10)
======================

LEVEL-0:
-------
        I logged into bandit game using SSH on port number 2220 and used the 
	  password as "bandit0". We need to find the password to next level using linux commands.
         Commands used: ls, cat
        "ls" command lists the files and ”cat [file]" displays the contents of the  specified file.
        Password for next level : "boJ9jbbUNNfktd78OOpsqOltutMc3MY1".   
     
LEVEL-1:
--------
        Commands used: ls, cat
        ls" command lists the files and ”cat [file]" displays the contents of the specified file.
        Password for next level : "CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9"

LEVEL-2:
-------
         Commands used: ls, cat
         In this level after taking the list we can infer that the  password is saved in the file named "spaces in this filename". since there is space  in the   name file given So we have to use double quotes to specify the file name.
Password for next level : "UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK".

LEVEL-3:
--------
         Commands used: cd,cat,ls
         In this level after using "ls" command a directory named inhere is  displayed.To move to the inhere directory "cd" command is used and used “ls” command but it returned nothing so i used ls -a and .hidden file was   displayed. Then used “cat” which displayed the password.
         Password for next level : "pIwrPrtPN36QITSp3EQaw936yaFoFgAB".

LEVEL-4:
--------
         Commands used: cd,cat,ls,file
         In this "ls" command displays a directory named inhere. Used “cd” to move to that directory and took the list which displays a lot of text  files. Used “file ./*” command to check into evey file that contain the wanted code and I found that only one file contains"ASCII text" so I used "cat ./-filename"command to read that particular file.
         Password for next level : "koReBOKuIDDepwhWk7jZC0RTdopnAYKh".

LEVEL-5:
-------
        Commands used: cd,cat,ls,find
        It is mentioned in the question that the flag is in inhere directory and some properties are mentioned that it is: human readable; 1033 bytes in size and not executable .
        After getting into inhere directory using cd I used "find -size 1033c ! -executable" and I found out the file specified : “./maybehere07/.file2”.
	  Then used “cat ./maybehere07/.file2”. find” is used to find any file or keyword from the whole system.
        Password for next level : "DxjZPULLxYr17uwoI01bNLQbtFemEgo7". 

LEVEL-6:
-------
         Commands used: cd,cat,ls,find
         Did ls but i got  no satisfactory result. So used cd then according to the some specifications given about the user ,group and size used the command:“ find /(root) -user bandit7 -group bandit6 -size 33c”. found many permission denied directories but among that there was one file not so. 
	   So used “ cat  /var/lib/dpkg/info/bandit7.password” and got the password.
         Password for next level : "HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs".

LEVEL-7:
-------
        Commands used : cat,grep,ls.
        First used “ls”  which displayed a data.txt. It was specified that it is near the word ”millionth”,so i used the command “ cat data.txt | grep "milliionth"”,which gave the password.“grep“ is used to find the matching pattern specified.
        Password for next level : "cvX2JJa4CFALtqS87jk27qwqGhBM9plV".

LEVEL-8:
-------
        Commands used: ls , cat , sort , uniq.
        Took list and it displayed “ data.txt “ then used the command “ cat  data.txt “ which displayed a lot of texts. But it was mentioned that the password was unique . So i used the command “ cat data.txt| sort|uniq -c ““sort” sorts the texts in an alphabetic order.“uniq –c“ displays the text in an order and counts the number of times it is repeated.
        Password for next level : “UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR”
           
LEVEL-9:
-------
        Commands used: ls , strings , grep.
        Did “ls” and it displayed the contents of data.txt then used  “strings data.txt| grep "="” as it was mentioned that the password was followed my “=”. SO the “grep” finds the matching pattern and displays the line.
        Password for next level : "truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk"

LEVEL-10:
--------
        Commands used: ls,cat,base64.
        Took list which displayed a data.txt file , then i did 
	  “cat data.txt | base64 -d” as it was aready mentioned that the file contains base64 encoded data. “base64 -d” will decodes the displayed content and gives the output which is the password.
        Password for next level : "IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR".
