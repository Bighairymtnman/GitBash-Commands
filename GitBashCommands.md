# Git Bash Commands Reference

## Navigation Commands

1. List directory contents:
   ```bash
   ls                  # List files and directories
   ls -l              # Detailed list view
   ls -a              # Show hidden files
   ```

2. Change directories:
   ```bash
   cd directory_name          # Move to specific directory
   cd ..                     # Move up one directory
   cd ~                      # Move to home directory
   pwd                      # Show current directory path
   ```




## File Operations

1. Create files and directories:
   ```bash
   touch filename.txt        # Create new file
   mkdir directory_name     # Create new directory
   mkdir -p path/to/dir    # Create nested directories
   ```

2. Copy and move:
   ```bash
   cp file1 file2          # Copy file1 to file2
   cp -r dir1 dir2        # Copy directory and contents
   mv file1 file2         # Move/rename file
   mv dir1 dir2          # Move/rename directory
   ```

3. Delete files and directories:
   ```bash
   rm filename            # Remove file
   rm -r directory       # Remove directory and contents
   rmdir directory      # Remove empty directory
   ```




## Text Viewing and Editing

1. View file contents:
   ```bash
   cat filename           # Display entire file
   less filename         # View file with scrolling
   head filename         # Show first 10 lines
   tail filename         # Show last 10 lines
   ```

2. Find text in files:
   ```bash
   grep "text" filename   # Search for text in file
   grep -r "text" .      # Search in all files recursively
   ```

3. Basic text editing:
   ```bash
   nano filename         # Open simple text editor
   echo "text" > file   # Write text to file (overwrite)
   echo "text" >> file  # Append text to file
   ```






## System Information Commands

1. System details:
   ```bash
   uname -a              # Show system information
   df -h                # Show disk space usage
   free -h              # Show memory usage
   top                  # Show running processes
   ```

2. User information:
   ```bash
   whoami               # Show current username
   id                   # Show user ID information
   who                  # Show who is logged in
   ```

3. Network information:
   ```bash
   ip addr              # Show IP addresses
   ping hostname        # Test network connection
   netstat -tuln       # Show network connections
   ```





## Permissions and Ownership

1. Change permissions:
   ```bash
   chmod +x filename     # Make file executable
   chmod 755 filename   # Set specific permissions
   chmod -R 755 dir    # Set permissions recursively
   ```

2. Change ownership:
   ```bash
   chown user filename           # Change file owner
   chown user:group filename    # Change owner and group
   chown -R user directory     # Change ownership recursively
   ```

3. View permissions:
   ```bash
   ls -l filename      # Show file permissions
   ls -ld directory   # Show directory permissions
   ```




## Utility Commands

1. Process management:
   ```bash
   ps                   # Show running processes
   kill process_id      # Stop a process
   killall process_name # Stop all processes by name
   ```

2. Archive and compression:
   ```bash
   tar -czf archive.tar.gz files/    # Create tar archive
   tar -xzf archive.tar.gz          # Extract tar archive
   zip -r archive.zip directory     # Create zip file
   unzip archive.zip               # Extract zip file
   ```

3. Command history:
   ```bash
   history             # Show command history
   !!                 # Repeat last command
   !number           # Run command by history number
   ```





## Shortcuts and Command Combinations

1. Keyboard shortcuts:
   ```bash
   Ctrl + C            # Stop current process
   Ctrl + L            # Clear screen
   Ctrl + R            # Search command history
   Ctrl + A            # Move to start of line
   Ctrl + E            # Move to end of line
   ```

2. Command combinations:
   ```bash
   command1 && command2   # Run command2 if command1 succeeds
   command1 || command2   # Run command2 if command1 fails
   command1 | command2    # Pipe output to next command
   ```

3. Quick navigation:
   ```bash
   cd -                # Go to previous directory
   pushd directory    # Push directory to stack
   popd              # Pop directory from stack
   ```







