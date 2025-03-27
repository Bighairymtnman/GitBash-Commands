# Advanced Git Bash Commands Reference

## Shell Scripting Fundamentals

1. Script basics:
   ```bash
   #!/bin/bash                   # Shebang line for bash scripts
   chmod +x script.sh           # Make script executable
   ./script.sh                 # Run script
   ```

2. Variables and arguments:
   ```bash
   variable="value"             # Assign variable
   echo $variable              # Use variable
   $1, $2, $3                 # Access script arguments
   $#                        # Number of arguments
   $@                       # All arguments as array
   ```

3. Conditional statements:
   ```bash
   if [ condition ]; then
       command
   elif [ condition ]; then
       command
   else
       command
   fi
   ```




## Advanced Text Processing

1. Using sed (Stream Editor):
   ```bash
   sed 's/old/new/' file         # Replace first occurrence
   sed 's/old/new/g' file       # Replace all occurrences
   sed -i 's/old/new/g' file   # Replace and save changes
   sed '1d' file              # Delete first line
   ```

2. Using awk:
   ```bash
   awk '{print $1}' file        # Print first column
   awk -F: '{print $1}' file   # Use custom delimiter
   awk 'NR==1 {print}' file   # Print specific line
   awk '{sum+=$1} END {print sum}' file  # Sum first column
   ```

3. Advanced grep:
   ```bash
   grep -E "pattern|pattern2" file   # Multiple patterns
   grep -v "pattern" file           # Inverse match
   grep -c "pattern" file          # Count matches
   grep -r "pattern" directory    # Recursive search
   ```





## Advanced Process Management

1. Job control:
   ```bash
   command &             # Run in background
   jobs                 # List background jobs
   fg %1               # Bring job to foreground
   bg %1              # Resume job in background
   ```

2. Process monitoring:
   ```bash
   ps aux              # Detailed process list
   pgrep process_name # Find process ID
   nice -n 10 command # Run with priority
   renice +1 -p PID  # Change priority
   ```

3. Resource limits:
   ```bash
   ulimit -a           # Show all limits
   ulimit -u 100      # Limit user processes
   timeout 10s command # Run with time limit
   watch command     # Monitor command output
   ```






## Advanced Networking Commands

1. Network diagnostics:
   ```bash
   traceroute hostname          # Trace packet route
   nslookup domain            # DNS lookup
   dig domain                # Detailed DNS info
   netstat -tupln           # Active connections
   ```

2. Network monitoring:
   ```bash
   tcpdump -i eth0            # Capture network traffic
   iftop                     # Monitor bandwidth
   ss -tuln                 # Socket statistics
   lsof -i                 # List network files
   ```

3. SSH operations:
   ```bash
   ssh-keygen -t rsa         # Generate SSH key
   ssh-copy-id user@host    # Copy SSH key to server
   scp file user@host:path  # Secure file copy
   rsync -av dir/ backup/  # Sync directories
   ```







## Advanced File System Operations

1. Find command operations:
   ```bash
   find . -name "*.txt" -type f     # Find files by name
   find . -mtime -7                # Files modified last week
   find . -size +100M             # Files larger than 100MB
   find . -exec command {} \;    # Execute command on files
   ```

2. Disk operations:
   ```bash
   dd if=/dev/sda of=backup.img    # Create disk image
   fdisk -l                       # List disk partitions
   mount -t type device dir      # Mount filesystem
   lsblk                       # List block devices
   ```

3. File system maintenance:
   ```bash
   fsck /dev/sda1                # Check filesystem
   tune2fs -l /dev/sda1         # View filesystem info
   badblocks -v /dev/sda1      # Check for bad blocks
   e2label /dev/sda1 label    # Label filesystem
   ```





## Advanced System Monitoring

1. Performance monitoring:
   ```bash
   vmstat 1                    # Virtual memory stats
   iostat -x 1               # I/O statistics
   sar -u 1 10              # CPU utilization
   dstat                   # System resource stats
   ```

2. Log monitoring:
   ```bash
   tail -f /var/log/syslog    # Live log viewing
   journalctl -f             # System journal logs
   logwatch                 # Log analysis report
   last                    # Login history
   ```

3. Resource tracking:
   ```bash
   strace command            # Trace system calls
   ltrace command          # Trace library calls
   lsof                   # List open files
   fuser -v /path        # Show file users
   ```







## Advanced Shell Customization

1. Shell environment:
   ```bash
   export VAR="value"          # Set environment variable
   set -o vi                  # Use vi mode in shell
   shopt -s globstar        # Enable advanced globbing
   bind '"\e[A": history-search-backward'  # Custom key binding
   ```

2. Prompt customization:
   ```bash
   PS1="\u@\h:\w\$ "          # Custom prompt format
   PROMPT_COMMAND="command"   # Execute before prompt
   eval "$(dircolors)"      # Custom ls colors
   source ~/.bashrc        # Reload configuration
   ```

3. Alias and function creation:
   ```bash
   alias ll='ls -la'          # Create command alias
   function mcd() {          # Create custom function
       mkdir -p "$1"
       cd "$1"
   }
   ```







## Advanced Debugging Techniques

1. Script debugging:
   ```bash
   set -x                     # Enable debug mode
   set -e                    # Exit on error
   set -u                   # Exit on undefined variable
   trap 'echo $LINENO' ERR  # Debug trap
   ```

2. Error handling:
   ```bash
   command || echo "Failed"    # Handle command failure
   command 2> error.log      # Redirect errors to file
   exec 2> >(logger)        # Log all errors
   set -o pipefail        # Check pipeline errors
   ```

3. Performance debugging:
   ```bash
   time command              # Measure execution time
   /usr/bin/time -v command # Detailed timing stats
   perf stat command       # Performance statistics
   valgrind command       # Memory debugging
   ```








