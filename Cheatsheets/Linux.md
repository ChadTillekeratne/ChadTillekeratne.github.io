## Linux Commands

# File Operations
- `ls -la`
  - Show all contents in a directory
- `rm -rf /path/to/my-folder`
  - Delete a directory with all contents
## File Permissions
- `chmod 666 myfile.txt`
  - `-rw------- (600)` - Only the user has read and write permissions
  - `-rw-r--r-- (644)` - Only user has read and write permissions; the group and others can read only.
  - `-rwx------ (700)` - Only the user has read, write and execute permissions
  - `-rwxr-xr-x (755)` - The user has read, write and execute permissions; the group and others can only read and execute
  - `-rwx--x--x (711)` - The user has read, write and execute permissions; the group and others can only execute
  - `-rw-rw-rw- (666)` - Everyone can read and write to the file
  - `-rwxrwxrwx (777)` - Everyone can read, write and execute
- `chown root /path/to/my-directory`
  - Change owner
- `chgrp group /path/to/my-directory`
  - Change group owner