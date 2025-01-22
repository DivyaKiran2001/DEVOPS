# Linux Operating System & Basics of Shell Scripting

## Operating System (OS)
The Operating System acts as a bridge between software and hardware, managing system resources and providing a user interface to interact with the computer.

---

## Shell Scripting in Linux
Shell scripting is the process of automating tasks by writing scripts to execute commands in sequence.

---

## Common Linux Commands

1. **Create a File**
   ```bash
   touch filename
   ```
   Example:
   ```bash
   touch first-shell-script.sh
   ```

2. **List Files**
   ```bash
   ls
   ```

3. **List Files with Additional Details**
   ```bash
   ls -ltr
   ```
   This lists files with additional details like timestamp and permissions.

4. **Manual for Commands**
   ```bash
   man [command]
   ```
   Example:
   ```bash
   man touch
   man ls
   ```
   Displays details about the specified command.

5. **Create and Edit a File**
   ```bash
   vim filename
   ```
   Opens a file in the `vim` editor where you can write contents to the file.

---

## Executable Scripts in Linux

Scripts start with a shebang (`#!`) followed by the path to the interpreter. Common interpreters include:

- `#!/bin/bash`
- `#!/bin/dash`
- `#!/bin/sh`
- `#!/bin/ksh`

Example:
```bash
#!/bin/bash
# This is a simple shell script
echo "Hello, World!"
```

Save the script and make it executable using:
```bash
chmod +x scriptname.sh
```

Run the script using:
```bash
./scriptname.sh ```




6. **echo** -----> To print the content

Ex : echo "hello"

* NOTE : 

(i) When you want to write the contents to the file press esc + i
(ii) After writing the content press enter to save the file.

:q  --> Quit the file
:wq --> Write and exit the file

7. cat filename                  -----> To print the content of the file

Ex : cat first-script-shell.sh

8. sh filename (or) ./filename   -----> To execute the file

9. chmod                         -----> To grant permissions to a file

can grant permissions to 

- To All Users (Everyone)
- Your group   (Group)
- You          (User)


421

4- Read
2- Write
1- Execute

Ex : chmod 444 first-script-shell.sh

Can only provide read access

10. history             ----> Gives the history of the commands used
    
11. pwd                 -----> Gives the present working  directory

** Creating folders:

12. mkdir directory_name  ---> To create a directory

Ex: mkdir myfirstfolder

13. cd directory_name ---> To change the directory

Ex: cd myfirstfolder

14. nproc             ---> The nproc command in Linux is used to display the number of available processing units (CPU cores) on the system

15. top               ---> The top command in Linux is an interactive, real-time system monitor that displays information about system processes, resource usage, and performance metrics.



    



