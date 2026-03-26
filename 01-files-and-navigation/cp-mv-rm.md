# Copying, Moving, and Deleting Files

## What it does
The `cp`, `mv`, and `rm` commands are used to copy, move, rename, and delete files and directories in Linux.

## Scenario
You need to back up a file before making changes, move files into the correct location, rename old logs, or remove files that are no longer needed.

## Copy a file
```bash
cp file.txt file-backup.txt
```

## Copy a directory
```bash
cp -r logs/ logs-backup/
```

## Move or rename a file
```bash
mv old.log archived.log
```

## Move a file to another directory
```bash
mv file.txt /home/darren/Documents/
```

## Delete a file
```bash
rm temp.log
```

## Delete a directory
```bash
rm -r old_logs/
```

## Force delete a directory
```bash
rm -rf temp/
```

## Verify changes
```bash
ls -l
```

## Notes
- `cp` copies files and directories
- `cp -r` is required when copying directories
- `mv` can move a file or rename it
- `rm` permanently deletes files
- `rm -r` deletes a directory and its contents
- `rm -rf` force deletes without prompting, so it should be used carefully

## Best practice
Back up important files before editing or deleting them.

```bash
cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.backup
```

## Common error

### Error message
```bash
cp: cannot stat 'file.txt': No such file or directory
```

### Example
![cp error](/images/cp-error.png)

### Cause
The file does not exist in the current directory, or the file path is incorrect.

### How to troubleshoot

Check your current directory:
```bash
pwd
```

List files to confirm the file exists:
```bash
ls -l
```

### Fix

If the file does not exist, create it:
```bash
touch file.txt
cp file.txt file-backup.txt
```

If the file exists in another location, use the full path:
```bash
cp /home/darren/Documents/file.txt file-backup.txt
```

## Real-world use
- backing up configuration files before making changes
- moving logs into archive folders
- renaming files to keep directories organised
- removing temporary or old files to free disk space

## Screenshot

### Copying and moving files
![copy and move](/images/cp-mv.png)

### Deleting files
![delete files](/images/rm.png)
