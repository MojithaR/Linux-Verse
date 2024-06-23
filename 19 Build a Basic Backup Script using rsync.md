# Building a Basic Backup Script using rsync

## Introduction

Data loss is a significant risk faced by individuals and organizations alike. Whether due to hardware failure, human error, or malicious attacks, losing critical data can have severe consequences. Implementing a backup strategy is essential to mitigate this risk and ensure data integrity and availability. `rsync` is a versatile command-line tool in Linux used for file synchronization and data backup, offering efficiency, flexibility, and powerful options for automating backups.

In this guide, we will walk through the process of building a basic backup script using `rsync`. This script will automate the task of copying files and directories from a source location to a backup destination, ensuring data redundancy and facilitating easy recovery in case of data loss.

## Steps to Follow

### Step 1: Install rsync (if not already installed)

Before creating the backup script, ensure that `rsync` is installed on your Linux system. Most Linux distributions come with `rsync` pre-installed, but you can verify and install it if necessary:

```bash
sudo apt update
sudo apt install rsync
```

### Step 2: Scripting the Backup Process

The core of our backup solution will be a shell script that utilizes `rsync` to synchronize data between a source directory (what we want to backup) and a destination directory (where backups will be stored).

#### Creating the Backup Script

1. **Open a text editor** (such as `nano` or `vim`) and create a new file for your backup script. Let's name it `backup.sh`.

   ```bash
   nano backup.sh
   ```

2. **Add the following content to `backup.sh`**:

   ```bash
   #!/bin/bash

   # Source and destination directories
   SRC="/path/to/source"
   DEST="/path/to/backup"

   # Execute rsync command for backup
   rsync -avz --delete $SRC $DEST

   # Optional: Add timestamp to log file
   echo "Backup completed on $(date)" >> /var/log/backup.log
   ```

   - Replace `/path/to/source` with the path of the directory or files you want to backup.
   - Replace `/path/to/backup` with the destination directory where backups will be stored.
   - The `rsync` command options:
     - `-a`: Archive mode (preserves permissions, timestamps, etc.).
     - `-v`: Verbose output (optional, for seeing detailed progress).
     - `-z`: Compress file data during transfer to reduce bandwidth.
     - `--delete`: Delete extraneous files from the destination directory.

3. **Save and exit the text editor** (`Ctrl + X`, then `Y` to confirm, and `Enter`).

4. **Make the script executable**:

   ```bash
   chmod +x backup.sh
   ```

### Step 3: Testing the Backup Script

Before scheduling the backup, it's essential to test the script to ensure it functions correctly.

1. **Run the backup script manually**:

   ```bash
   ./backup.sh
   ```

   - This command executes the `backup.sh` script and initiates the backup process as defined.

2. **Verify that files are copied** to the destination directory (`/path/to/backup`) and ensure there are no errors reported.

### Step 4: Scheduling Backups using cron

Automating backups ensures regular and consistent data protection. We will use `cron`, a time-based job scheduler in Unix-like operating systems, to schedule our backup script to run automatically at specified intervals.

#### Setting up a cron Job

1. **Edit the `cron` jobs for the current user**:

   ```bash
   crontab -e
   ```

2. **Add a `cron` job to schedule the backup**. For example, to run the backup script daily at 2 AM:

   ```cron
   0 2 * * * /path/to/backup.sh
   ```

   - Adjust the schedule (`0 2 * * *` means every day at 2 AM) according to your preference.

3. **Save and exit the editor** (`Ctrl + X`, then `Y` to confirm, and `Enter`).

### Step 5: Implementing Error Handling

Handling errors gracefully ensures the reliability of our backup solution. We can enhance our script to capture and log any errors that may occur during the backup process.

#### Updating the Backup Script with Error Handling

```bash
#!/bin/bash

# Source and destination directories
SRC="/path/to/source"
DEST="/path/to/backup"

# Log file path
LOG="/var/log/backup.log"

# Function to log messages with timestamp
log_message() {
    echo "$(date +'%Y-%m-%d %H:%M:%S') $1" >> $LOG
}

# Execute rsync command for backup
rsync -avz --delete $SRC $DEST >> $LOG 2>&1

# Check rsync exit status
RSYNC_EXIT_STATUS=$?

if [ $RSYNC_EXIT_STATUS -eq 0 ]; then
    log_message "Backup completed successfully."
else
    log_message "Backup failed with error code $RSYNC_EXIT_STATUS."
fi
```

- In this updated script:
  - Errors and regular output from `rsync` are redirected to the log file (`$LOG`).
  - After running `rsync`, the script checks the exit status (`$?`). If `rsync` completes successfully (exit status `0`), a success message is logged. Otherwise, an error message with the exit status is logged.

### Step 6: Monitoring Backup Logs

Logging backup activities provides visibility into the backup process, aiding in troubleshooting and monitoring.

1. **Create a log file** if it doesn't exist:

   ```bash
   sudo touch /var/log/backup.log
   sudo chmod 644 /var/log/backup.log
   ```

2. **View the backup log** to monitor backup activities and review any errors:

   ```bash
   tail -f /var/log/backup.log
   ```

   - This command displays the last 10 lines of the log file (`-f` option follows new entries).

## Advanced Configurations and Options

### 1. Excluding Files and Directories

You may want to exclude certain files or directories from being backed up. Use the `--exclude` option with `rsync`:

```bash
rsync -avz --delete --exclude='*.log' $SRC $DEST
```

This example excludes all files with the `.log` extension from being copied.

### 2. Bandwidth Limitation

To limit the bandwidth used by `rsync` during backups, use the `--bwlimit` option:

```bash
rsync -avz --delete --bwlimit=1000 $SRC $DEST
```

This limits the bandwidth to 1000 KB/s (kilobytes per second).

### 3. Remote Backups via SSH

`rsync` can securely synchronize files between local and remote systems using SSH:

```bash
rsync -avz --delete -e ssh user@remotehost:/path/to/source /path/to/backup
```

Replace `user@remotehost` with the SSH username and hostname of the remote system.

## Summary

Creating a basic backup script using `rsync` in Linux is a fundamental step towards ensuring data integrity and availability. By following the steps outlined in this guide, you can automate the backup process, schedule backups using `cron`, implement error handling and logging, and explore advanced configurations to customize your backup solution according to specific needs.

Regular backups are crucial for protecting against data loss due to hardware failures, accidental deletions, or security breaches. With `rsync`, you have a powerful tool at your disposal to create reliable and efficient backup solutions tailored to your requirements.

This guide provides a solid foundation for building and managing backup scripts in Linux, equipping you with essential skills for data protection and system administration tasks. Incorporate these practices into your workflow to maintain data resilience and ensure business continuity in any Linux environment.

By mastering `rsync` and scripting backup processes, you empower yourself with the ability to safeguard critical data effectively, making you a proficient Linux administrator capable of handling data backup and recovery challenges with confidence.

