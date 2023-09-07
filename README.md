# Into to Linux Commands

1. `ls`: List files and directories in the current directory.
2. `mkdir`: Create a new Folder in current directory.
    
    ```bash
    mkdir folderName
    ```
    
    Create a subfolder:
    
    ```bash
    mkdir currFolder
    
    mkdir currFolder/subFolder
    ```
    
3. `cd`: Change directory
    
    ```bash
    cd directoryName
    ```
    
4. `cd ..`: Exit the current directory and go back to previous directory
5. `echo`: Built in command in home bin directory. It’s used to display values and variables in the shell
    
    ```bash
    echo "first" && echo "second"
    ```
    
    Here second will be printed only after the first is printed
    
    When you wanna add multiple commands in the same line, you can use `;` to seperate commands
    
    Example:
    
    ```bash
    whoami;echo "Hello"
    ```
    
    ```bash
    echo "one" || echo "two"
    ```
    
    Here `one` will be printed only
    
    ```bash
    echo "hey" >> file.txt
    ```
    
    This will append `hey` to this file
    
    ```bash
    echo "hey" > file.txt
    ```
    
    This will remove all other contents from the file and only appened `hey` to the file (That’s mean it will overwrite the file) 
    
    ```bash
    echo "hey" && {echo "hi";echo "I am good"}
    ```
    
    OutPut:
    
    ```bash
    hey
    hi
    I am good
    ```
    
    Basically It’s a combination operator
    
6. `pwd`: Print the working directory (displays the current directory)
7. `whereis:` It is a command to find the location of any file
    
    ```bash
    whereis git
    ```
    
8. `open filePath`:  It is a command to open a folder with its path
    
    ```bash
    open /usr/bin
    ```
    
9. `ls -a`: To see hidden files of the current directory
    
    ```bash
    ls -a
    ```
    
10. `ls -R`: Show the files and directories recursively (that’s mean it will also show the files that are in subdirectories)
    
    ```bash
    ls -R
    ```
    
11. `cat`: Display the content of a file.
    
    ```bash
    cat file.txt
    ```
    
    Creating Two files and merging it into 1 file
    
    ```bash
    cat > file1.txt
    
    -- write text here
    
    -- ctrl + c
    
    cat > file2.txt
    
    -- write text here
    
    -- ctrl + c 
    
    cat file1.txt file2.txt > file3.txt
    
    cat file3.txt
    
    -- printed content of file 3
    ```
    
12. `man`: Command to know information of a particular command
    
    ```bash
    man ls
    ```
    
13. `tr`: Translate or delete characters from input
    
    ```bash
    echo "Hello" | tr 'H' 'h'
    ```
    
    Translete the contents of a file from lowercase to uppercase and copy the contents to another file. Here `tr` command is used to translet from lower case to upper case. `>` is known as redirection. `|` is known as pipe.
    
    ```bash
    cat file.txt
    
    -- write text
    
    cat file.txt | tr a-z A-Z > upperCase.txt
    
    cat upperCase.txt
    
    -- printed text
    ```
    
14. `touch`: Create an new file 
    
    ```bash
    touch file.txt
    ```
    
15. `cp`: Copy files or directories
    
    ```bash
    cp sourceFile targetFile
    ```
    
    `cp -R`: Copy directories recursively.
    
    ```bash
    cp -R source_directory /path/to/destination
    ```
    
    Copy the files and folders from a folder and paste it to another folder
    
    ```bash
    cp -R fileOrFolderName destinationFolderName
    ```
    
16. `mv`: Move or rename files or directories.
    
    ```bash
    mv file.txt newFile.txt
    ```
    
    Move a file into a folder
    
    ```bash
    mv file.txt folderName
    ```
    
    Move a subfolder to the current directory
    
    ```bash
    mv folder/subFolder .
    ```
    
    Move multiple files into a directories
    
    ```jsx
    mv file1.txt file2.txt file3.txt -t destination
    ```
    
17. `rm`: Remove or delete files or folder permanently
    
    ```bash
    rm file.txt
    ```
    
    Deleting a directory: To delete a directory, you can use 
    
    ```bash
    rm -r directory_name
    ```
    
    Delete a file forcefully
    
    ```bash
    rm -rf fileName
    ```
    
    Deleted all the files permanently except a particular file
    
    ```bash
    rm -r !(file.txt)
    ```
    
    Deleting all the files and folders from a directory
    
    ```jsx
    rm -r !()
    ```
    
18. `df`: Display disk space usage.
    1. To see the values in mb we use: `df -m`
    2. To see the values in gb, we use: `df -g`
    
    ```bash
    df -h
    ```
    
19. `du`: Displays the disk usage statistics
20. `du -h`: Displays disk usage statistics in human readable format
21. `head`: Display the beginning of a file (First 10 lines will be shown).
    
    ```bash
    head file.txt
    ```
    
    Display the first 4 lines of file text
    
    ```bash
    head -n 4 file.txt
    ```
    
22. `tail`: Display the end of a file (Last 10 lines will be shown).
Example: `tail file.txt`
    
    Display the last 2 lines of file text
    
    ```bash
    tail -n 2 file.txt
    ```
    
23. `diff`: Compare files line by line and outputs the contents that don’t match
    
    ```bash
    diff file1.txt file2.txt
    ```
    
24. `locate`: To Find any files or folder.
    
    ```bash
    locate file.txt
    ```
    
25. Find all the text files (Here `*` means any name can come in the place of `*` )
    
    ```bash
    locate "*.txt"
    ```
    
26. `find`: Search for files and directories based on various criteria.
    
    ```bash
    find folderName -name "*.txt"
    ```
    
    Here I am finding files which are text files in that folder
    
    Find files in the current directory
    
    ```bash
    find .
    ```
    
    Find files in the previous directory
    
    ```bash
    find ..
    ```
    
    Find files inside a particular directory
    
    ```bash
    find folderName
    ```
    
    Find only the directories and not the files of the current directory
    
    ```bash
    find . -type d
    ```
    
    Find only the files and not the folders of the current directory
    
    ```bash
    find . -type f
    ```
    
    Find a particular file in the current directory with its name (Here the name of the file is case sensitive)
    
    ```bash
    find . -type f -name "fileName.txt"
    ```
    
    Suppose if I want to find files with the name “two”, then we will do this below code. Here `*` means anything can come over here.
    
    ```bash
    find . -type f -name "two*"
    ```
    
    If I don’t want the name to be case sensitive then we will use this
    
    ```bash
    find . -type f -iname "fileName.txt"
    ```
    
    Find files modified less than 20 minutes ago in the current directory
    
    ```bash
    find . -type f -mmin -20
    ```
    
    Find files modified more than 15 minutes ago in the current directory
    
    ```bash
    find . -type f -mmin +15
    ```
    
    Find files modified more than 2 min ago and less than 10 min ago in the current directory
    
    ```bash
    find . -type f -mmin +2 -mmin -10
    ```
    
    Find files modified less than 10 days ago in the current directory
    
    ```bash
    find . -type f -mtime -10
    ```
    
    Find files in the current directory of size more than 1kb
    
    ```bash
    find . -size +1kb
    ```
    
    Find files that are empty in current directory
    
    ```bash
    find . -empty
    ```
    
    Find all the files in the current directory whose permission is set to 777
    
    ```bash
    find . -perm 777
    ```
    
27. File permissions: Linux uses permissions to control who can access files and what actions they can perform.
    
    There are three types of file permission:
    
    - Read (r)
    - Write (w)
    - Execute (x)
    
    To check the permission alloted to a file
    
    ```bash
    ls -l file.txt
    ```
    
    Changing file permissions: You can use `chmod` command to change file permissions.
    Example: `chmod 644 file.txt` (gives read and write permission to the owner, and read-only permission to group and others)
    
    ```bash
    chmod u=rwx,g=rx,o=r file.txt
    ```
    
    - `u` stand for User
    - `g` stands for group
    - `o` stands for other
    
    <aside>
        
    📌 Here I’m giving Read (r), Write (w) and Execute (x) permission to User, Read (r) and Execute (x) permission to Group, Read (r) only permission to Other
    
    </aside>
    
    If you want to use numbers instead of u, g, x then 
    
    - `4` stands for Read
    - `2` stands for write
    - `1` stands for execute
    - `0` stands for no permission
    - `7` stands for all Read, write and execute permission
    
    If I want to use numbers instead of u, g, x for the above written command
    
    ```bash
    chmod 754 file.txt
    ```
    
28. `chown`: Change file ownership.
    
    ```bash
    chown new_owner file.txt
    ```
    
29. `whoami`: It’s used to check which person is logged in and display the name
30. Performing an action on multiple files: Use wildcards like `*` to perform actions on multiple files simultaneously.
    
    ```bash
    rm *.txt
    ```
    
    Here I am removing all files with ".txt" extension
    
    Remove multiple files of type .txt at the same time from the current directory
    
    ```bash
    find . -type f -name "*.txt" -exec rm -rf {} +
    ```
    
31. `grep`: Search for a specific pattern in a file. (It’s case sensitive)
    
    ```bash
    grep "search_term" file.txt
    ```
    
    Checking the version of the `grep`
    
    ```bash
    grep -V
    ```
    
    ```bash
    grep -w "writePattern" file.txt
    ```
    
    Show (Search) the complete word in the file
    
    Suppose in the file, I have saved my name: Manash Roy. I will give only Mana or Manash It’ll show me complete name
    
    ```bash
    grep -w "Mana" file.txt
    ```
    
    As this `grep` is case sensitive so we will use below command
    
    ```bash
    grep -i "writePattern" file.txt
    ```
    
    ```bash
    grep -iw "writePattern" file.txt
    ```
    
    Find the line number with text
    
    ```bash
    grep -n "searchPattern" file.txt
    ```
    
    Combining all the three types `grep` commands
    
    ```bash
    grep -win "searchPattern" file.txt
    ```
    
    To see the previous three lines we can write
    
    ```bash
    grep -B 3 "searchPattern" file.txt
    ```
    
    To search for the pattern in all the text files of the current directory, we can write
    
    ```bash
    grep -win "searchPattern" ./*.txt
    ```
    
    Check all the files containing some pattern in the current directory
    
    ```bash
    grep -wirl "pattern" .
    ```
    
    Count the number of files containing some pattern in the current directory
    
    ```bash
    grep -wirc "pattern" .
    ```
    
32. `history`: To see the history of all the commands we have been using.
    
    ```bash
    history
    ```
    
    Show the history of all the commands having `ls`
    
    ```bash
    history | grep "ls"
    ```
    
33. `sort` : Sort the content of a text file in Alphabetical Order
    
    ```bash
    sort file.txt
    ```
    
    Sort the content of text file in case insensitive manner
    
    ```bash
    sort -f file.txt
    ```
    
    Sort the contents of a text file in numerical order
    
    ```bash
    sort -n file.txt
    ```
    
34. `jobs` : This command is used to display all the current jobs that are running along with the statuses. Job is a process that are started by the shell.
    
    ```bash
    jobs
    ```
    
35. `ping` : We can use ping command for your connectivity status and it’s basically going to connect us to the server and get all the information 
    
    ```bash
    ping google.com
    ```
    
    In this case, It will connect to the google.com
    
36. `wget`: Download files from the internet.
Example: `wget <https://example.com/file.txt>`
    
    ```bash
    wget URL
    ```
    
    To give a user defined file name to the file to be dowloaded, take the help of the following example
    
    ```bash
    wget -o myFile.pdf URL
    ```
    
37. `top`: We can use this command in order to find all the processes that are running currently and how many CPU usage is taking
38. `zip` : Make files Compressed and  zip them into one
    
    ```bash
    zip file.zip fileName.txt
    ```
    
    ```bash
    zip file.zip file1.txt file2.txt
    ```
    
39. `unzip` : Unzip files
    
    ```bash
    unzip file.zip
    ```
    
40. `kill` : Killing a process which is running
    
    ```bash
    kill processID
    ```
    
41. `hostname`: It is used to obtain the domain name system (DNS) and get the information of that domain
Example: `hostname`
    
    ```bash
    hostname -i
    ```
    
    It will give the IP address
    
42. `useradd`: Add a new user
    
    ```bash
    useradd userName
    ```
    
43. `userdel`: Delete a user
    
    ```bash
    userdel oldUsername
    ```
    
44. `passwd` : Setting Password for new User Added
    
    ```bash
    passwd User
    ```
    
45. `uname`: Get the operating system name
    
    ```bash
    uname
    ```
    
    Get the type of Operating System
    
    ```bash
    uname -o
    ```
    
    Get the architecture type of operating system
    
    ```bash
    uname -m
    ```
    
    Get the kernel version
    
    ```bash
    uname -r
    ```
    
    Get all the information about the system
    
    ```bash
    cat /etc/os-release
    ```
    
46. `lscpu`: Display information about the CPU.
    
    ```bash
    lscpu
    ```
    
47. `free`: Check the memory that is free.
    
    ```bash
    free
    ```
    
    Check the used and free memory in human readable format 
    
    ```bash
    free -h
    ```
    
48. `vmstat` : Check the virtual memory
    
    ```bash
    vmstat
    ```
    
    To display this virtual memory in mbs, write the following
    
    ```bash
    vmstat -S m
    ```
    
49. `id`: Display user and group information.
    
    ```bash
    id
    ```
    
    ```bash
    id -g
    ```
    
    ```bash
    id -G
    ```
    
    ```bash
    id -r
    ```
    
50. `id User`: Display information about a specific user.
    
    ```bash
    id User
    ```
    
51. `getent`: Check if a user exists or not
    
    ```bash
    gatent group USER
    ```
    
52. `lsof`: List all the open files.
    
    ```bash
    lsof
    ```
    
    List all the open files that are opened by a particular user
    
    ```bash
    lsof -u USER
    ```
    
53. `nslookup`:  It is used to checkout the IP address for a particular domain
    
    ```bash
    nslookup google.com
    ```
    
    If I write
    
    ```bash
    nslookup IP_ADDRESS
    ```
    
    Then it will give more info of the same (What I got after writing nslookup google.com)
    
54. `netstat`: Print all the ports that are currently up
    
    ```bash
    netstat
    ```
    
55. `sed`: Stream editor for text manipulation.
Example: `sed 's/old/new/' file.txt`
56. `cut`: It is used to cut out selected portions of each line of a file
    
    ```bash
    cut -c 1-2 file.txt
    ```
    
    This will cut out first 2 column of each line of the file
    
57. `htop`: It allows the user to interactively monitor the system’s vital resources or server’s processes in real time 
Example: `htop`
58. `ps aux`: Display information about running processes alogn with the process id.
59. `alias` command: Create shortcuts or aliases for commands.
Example: `alias ll='ls -al'` (creates an alias 'll' for 'ls -al')
