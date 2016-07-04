# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
/home/cabox/workspace  

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
LICENSE    challenge_files        nix_scavenger_hunt_stretch.md    README.md  nix_scavenger_hunt.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?* total 36K                                                                      
drwxrwxr-x  4 cabox cabox 4.0K Jul  3 22:23 .                                   
drwxr-xr-x 11 cabox cabox 4.0K Jul  3 22:23 ..                                  
drwxrwxr-x  8 cabox cabox 4.0K Jul  3 22:57 .git                                
-rw-rw-r--  1 cabox cabox 1.1K Jul  3 22:23 LICENSE                             
-rw-rw-r--  1 cabox cabox 1.4K Jul  3 22:23 README.md                           
drwxrwxr-x  7 cabox cabox 4.0K Jul  3 22:23 challenge_files                     
-rw-rw-r--  1 cabox cabox 5.6K Jul  3 23:02 nix_scavenger_hunt.md               
-rw-rw-r--  1 cabox cabox  317 Jul  3 22:23 nix_scavenger_hunt_stretch.md

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: )Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?* 
-a will list all files including hidden files (files with names beginning with a dot)
-l gives a long listing of all files
-h print sizes in human readable format (e.g., 1K 234M 2G)

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr                   
boot  etc  home      lib64  mnt    proc  run   srv   tmp  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/home/cabox                                                                     

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?* 
3 '.demo' files.

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
/home/cabox/workspace

* Press the up arrow on your keyboard. *What just happened?*
went to previous command, 'pwd'

* Press the up arrow a few more times. *What do you see?*
scrolling throught all previous commands one by one

* Run the `history` command. *What do you see?*
a list of the history of all the commands in the terminal

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox

* Discover who else is on your system with the `who` command.

*Are any other users using your system? If so, list them here:*
cabox    pts/0        Jul  4 00:42 (54.186.244.104)                             
cabox    pts/1        Jul  4 00:42 (54.186.244.104)                             
cabox    pts/2        Jul  4 00:42 (54.186.244.104)                             
cabox    pts/3        Jul  4 00:42 (54.186.244.104)                             
cabox    pts/4        Jul  4 00:45 (54.186.244.104)                             
cabox    pts/5        Jul  4 00:46 (54.186.244.104)                             
cabox    pts/7        Jul  4 00:50 (54.186.244.104)


* How long has your system been running? Use `uptime` to see, and *paste the result here:*
 00:58:00 up 15 min,  7 users,  load average: 0.00, 0.00, 0.00                  

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?* 
* It looks like it's showing all the users and their resource usage and all processes *

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
* This looks like it's showing all the users and their memory usage and the system's storage and data usage, as well as the current uptime *

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
2 files credit_cards.txt  credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
The date is 01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/modi_laboriosam.txt
 
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* 
2 files 
Britt-Erdman.user:O'Harachester, WA 37261                                       
Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
All of the user file names listed alphabetically

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
Able to view the files one page at a time and scroll through each page one by one. It's much easier to view the files this way
 
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
root       527  0.0  0.6  63876  3480 ?        Ss   00:42   0:00 sshd: cabox [pr
iv]                                                                             
root       529  0.0  0.6  63876  3480 ?        Ss   00:42   0:00 sshd: cabox [pr
iv]                                                                             
root       530  0.0  0.6  63876  3480 ?        Ss   00:42   0:00 sshd: cabox [pr
iv]                                                                             
root       533  0.0  0.6  63876  3476 ?        Ss   00:42   0:00 sshd: cabox [pr
iv]                                                                             
cabox      535  0.0  0.2  63876  1468 ?        S    00:42   0:00 sshd: cabox@pts
/0                                                                              
cabox      536  0.0  0.2  63876  1464 ?        S    00:42   0:00 sshd: cabox@pts
/1                                                                              
cabox      537  0.0  0.2  63876  1468 ?        S    00:42   0:00 sshd: cabox@pts
/2                                                                              
cabox      538  0.0  0.2  63876  1464 ?        S    00:42   0:00 sshd: cabox@pts
/3                                                                              
cabox      539  0.0  0.8  20632  4552 pts/0    Ss+  00:42   0:00 -bash          
cabox      549  0.0  0.8  20632  4552 pts/1    Ss+  00:42   0:00 -bash          
cabox      553  0.0  0.8  20632  4556 pts/2    Ss+  00:42   0:00 -bash          
cabox      688  0.0  0.8  20632  4556 pts/3    Ss+  00:42   0:00 -bash          
root      1327  0.0  0.6  63876  3476 ?        Ss   00:45   0:00 sshd: cabox [pr
iv]                                                                             
cabox     1329  0.0  0.2  63876  1464 ?        S    00:45   0:00 sshd: cabox@pts
/4                                                                              
cabox     1330  0.0  0.8  20632  4556 pts/4    Ss+  00:45   0:00 -bash          
root      1527  0.0  0.6  63876  3476 ?        Ss   00:46   0:00 sshd: cabox [pr
iv]                                                                             
cabox     1529  0.0  0.2  63876  1464 ?        S    00:46   0:00 sshd: cabox@pts
/5                                                                              
cabox     1530  0.0  0.8  20632  4556 pts/5    Ss+  00:46   0:00 -bash          
root      1933  0.0  0.6  63876  3480 ?        Ss   00:50   0:00 sshd: cabox [pr
iv]                                                                             
cabox     1935  0.0  0.2  64008  1492 ?        S    00:50   0:00 sshd: cabox@pts
/7                                                                              
cabox     1936  0.0  0.8  20636  4576 pts/7    Ss   00:50   0:00 -bash          
root      2171  0.0  0.6  63876  3340 ?        Ss   01:42   0:00 sshd: cabox [pr
iv]                                                                             
cabox     2173  0.0  0.2  64008  1488 ?        S    01:42   0:00 sshd: cabox@not
ty                                                                              
cabox     2174  0.0  0.1  12776   852 ?        Ss   01:42   0:00 /usr/lib/openss
h/sftp-server                                                                   
cabox     2178  0.0  0.2  15520  1140 pts/7    R+   01:57   0:00 ps aux         
cabox     2179  0.0  0.1   8816   764 pts/7    S+   01:57   0:00 grep --color=au
to cabox                              
