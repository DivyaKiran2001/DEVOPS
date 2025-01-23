# Linux Commands and Scripting Guide

## Common Commands

1. **`set -x`**
   - Enables debug mode in a script, showing the execution details of each command.

2. **`ps -ef`**
   - Lists all running processes with detailed information.

3. **`grep`**
   - Searches for patterns within text files or input.
   - Stands for Global Regular Expression Print.
   - Example:
     ```bash
     ps -ef | grep amazon
     ```

4. **Pipe (`|`)**
   - Sends the output of one command to another as input.
   - Example:
     ```bash
     ps -ef | grep amazon
     ```

5. **`date`**
   - Prints the current date and time.

6. **`awk`**
   - A text processing tool for searching, manipulating, and analyzing text.
   - Example:
     ```bash
     ps -ef | grep amazon | awk -F" " '{print $1}'
     ```
     Outputs the first column of the result.

7. **`set -e`**
   - Exits the script immediately if a command returns a non-zero exit status.

8. **`set -o pipefail`**
   - Ensures that the exit status of a pipeline reflects the exit status of the last failed command.

9. **`curl`**
   - Transfers data from or to a server using various protocols like HTTP, HTTPS, FTP, etc.

10. **`wget`**
    - Downloads files from the web via the command line.

11. **`find`**
    - Searches for files and directories based on criteria like name, type, size, and permissions.
    - Example:
      ```bash
      find /path/to/search -name "filename"
      ```
      Example to find a file named `pam`:
      ```bash
      find / -name pam
      ```

12. **`trap`**
    - Intercepts and handles signals or system events in shell scripts.

---

## Conditionals and Looping in Shell Scripts

### 1. **If-Else Statement**
```bash
if [expression]
then 
    # Commands if condition is true
else
    # Commands if condition is false
fi
```

### 2. **For Loop**
```bash
for variable in {start..end}
do 
   # Commands to execute in each iteration
done
```
Example:
```bash
for i in {1..100}
do
   echo $i
done
