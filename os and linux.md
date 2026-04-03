<details>
<summary> Basic Linux Commands </summary>
</br>
General Operations: 

- clear = Clears the terminal

Directory commands:

- pwd = Show current directory. Example Output: /Users/trupti
- ls = List folders and files. Example Output: Desktop  Downloads  Pictures  Documents
- cd [dirname] = Change directory to [dir]
- mkdir [dirname] = Make directory [dirname]
- cd .. = Go up a directory

File Operations:

- touch [filename] = Create [filename]
- rm [filename] = Delete [filename]
- rm -r [dirname] = Delete a non-empty directory and all the files in it
- rm -d [dirname] or rmdir [dirname] = Delete an empty directory

Navigating in the File System:

- cd usr/local/bin = Navigate multiple dirs . Move to bin directory
- cd ../.. = Move up 2 hierarchies, so go to 'usr' directory
- cd /usr = Alternative to go to 'usr' directly (absolute path)
- cd [absolute path] = Move to any location by providing the full path
- cd ~ = Shortcut alternative to go to home directory
- ls /etc/network = List folders and files of 'network' directory

More File and Directory Operations

- mv [filename] [new_filename] = Rename the file to a new file name
- cp -r [dirname] [new_dirname] = Copy dirname to new_dirname recursively meaning including the files
- cp [file] [new_file] = Copy file to new_file

Some more useful commands

- ls -R [dirname] = Show dirs and files also sub dirs and files
- history = Gives a list of all past commands in the current terminal session
- CTRL + r = Search history
- CTRL + c = Stop current command
- CTRL + SHIFT + v = Paste copied text to terminal
- ls -a = See hidden files too
- cat [filename] = Display the file content
- cat .bash_history Display the .bash_history content
- cat Documents/java-app/Readme.md Display the Readme.md file content at Document/java-app/Readme.md

Display OS Information

- uname -a = Show system and kernel

Execute commands as superuser

- sudo [some command] = Allows regular users to run programs with the security privileges of the superuser or root

</details>

******

<details>
<summary> Package Manager - Installing Software on Linux</summary>
<br />

APT Package Manager:
- `sudo apt search [package_name]` = Search for a given package
- `sudo apt install [package_name]` = Install a given package
- `sudo apt install [package_name] [package_name2]` = Install multiple packages with one command
- `sudo apt remove [package_name]` = Remove installed package
- `sudo apt update` = Updates the package index. Pulls the latest change from the APT repositories
- 
</details>

******
<details>
<summary> Vim Editor </summary>
<br />

- `sudo apt install vim` = Search for a given package

Vim Commands:
- `vim [filename]` = Open file with Vim
- `Press i key` = Switch to Insert Mode
- `Press esc key` = Switch to Command Mode
- `Type :wq` = Write File to disk and quit Vim
- `Type :q!` = Quit Vim without saving the changes
- `Type dd` = Delete entire line
- `Type d10` = Delete next 10 lines
- `Type u` = Undo
- `Type A` = Jump to end of line and switch to insert mode
- `Type 0` = Jump to start of the line
- `Type $` = Jump to end of the line
- `Type 12G` = Go to line 12
- `Type /pattern` = Search for pattern, e.g. `/india`
    - `Type n` = Jump to next match
    - `Type N` = Search in opposite direction
- `Type :%s/old/new` = Replace 'old' with 'new' throughout the file

</details>

******

<details>
<summary>Linux Accounts & Groups, File Ownership and Permission </summary>
 <br />

**Locations of Access Control Files:**
- /etc/passwd
- /etc/group

- `ls -l` = Print files in a long listing format, you can see ownership and permissions of the file

**Ownership:**
- `sudo chown [username]:[groupname] [filename]` = Change ownership
- `sudo chown trupti:admin names.txt` = Change ownership of 'names.txt' file to 'admin'
- `sudo chgrp devops test.txt` = Make 'devops' group owner of test.txt file

**Possible File Permissions (Symbolic):**
- r = Read
- w = Write
- x = Execute
- '-' = No permission

**Change File Permissions for different owners**

File Permissions can be changed for:
- u = Owner
- g = Group
- o = Other (all other users)

Minus (-) removes the permission
- `sudo chmod -x api` = Takes 'execute' permission away for 'api' folder from all owners
- `sudo chmod g-w config.yaml` = Takes 'write' permission away for 'config.yaml' file from the group 

Plus (+) adds permission
- `sudo chmod g+x config.yaml` = Add 'execute' permission for 'config.yaml' file to the group 
- `sudo chmod u+x script.sh` = Add 'execute' permission for 'script.sh' file to the user 
- `sudo chmod o+x script.sh` = Add 'execute' permission for 'script.sh' file to other 

Change multiple permissions for an owner
- `sudo chmod g=rwx config.yaml` = Assign 'read write execute' permissions to the group
- `sudo chmod g=r-- config.yaml` = Assign only 'read' permission to the group

Changing permissions with numeric values

[Absolute vs Symbolic Mode](https://docs.oracle.com/cd/E19455-01/805-7229/6j6q8svd8/)

- 0 = No permission
- 1 = Execute
- 2 = Write
- 3 = Execute + Write
- 4 = Read
- 5 = Read + Execute
- 6 = Read + Write
- 7 = Read + Write + Execute
<!-- -->
- `sudo chmod 777 script.sh` = rwx (Read, Write and Execute) permission for everyone for file 'script.sh'
- `sudo chmod 740 script.sh` = Give user all permissions (7), give group only read permission (4), give no permission (0)

</details>

******
<details>
<summary> Shell Scripting </summary>
 <br />

Create and open setup.sh file in vim editor: 

`vim setup.sh`

In setup.sh file:

```sh
#!/bin/bash

echo "Setup and configure server"

#save file with 
ESC :wq 

#make file executable
chmod u+x setup.sh

#execute script
./setup.sh 
bash setup.sh
```
**Variables :** 
```sh
#!/bin/bash

echo "Setup and configure server"

file_name=config.yaml
config_files=$(ls config)

echo "using file $file_name to configure something"
echo "here are all configuration files: $config_files"

```
**Conditions and User Input :**

```sh
#!/bin/bash

echo "Setup and configure server"

config_dir=$1

if [ -d "$config_dir" ]
then
 echo "reading config directory contents"
 config_files=$(ls "$config_dir")
else
 echo "config dir not found. Creating one"
 mkdir config_dir
 touch "config_dir/config.sh"
 echo "config.sh created"
fi

echo "Reading user input"

read -p "Please enter your password: " user_pwd
echo "thanks for your password $user_pwd"

echo "all params: $*"
echo "number of params: $#"

echo "user $1"
echo "group $2"
```
Executing the bash file 

bash setup.sh name lastname

</details>

******

<details>
<summary> Environment Variables </summary>
 <br />

</details>

 ******

<details>
<summary> Networking  </summary>
 <br />
 Useful Networking Commands:

- `ip` = one of the basic commands
- `ifconfig` = for configuring and troubleshooting networks. 
- `netstat` = tool for printing network connections, routing tables
- `ps aux` =
 - ps = displays information about a selection of the active processes
 - a = show processes for all users
 - u = display the process's user/owner
 - x = also show processes not attached to a terminal

</details>

 ******

<details>
<summary> SSH Shell </summary>
 <br />

</details>

  ******
