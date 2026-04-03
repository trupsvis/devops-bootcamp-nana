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
