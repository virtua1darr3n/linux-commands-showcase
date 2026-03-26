# find

## What it does
The `find` command is used to search for files and directories based on name, type, size, or modification time.

## Scenario
You need to locate log files, find old files for cleanup, or search for configuration files across a system.

## Find a file by name
```bash
find . -name "file.txt"
```

## Find all .log files
```bash
find /var/log -name "*.log"
```

## Case-insensitive search
```bash
find . -iname "file.txt"
```

## Find directories only
```bash
find . -type d
```

## Find files only
```bash
find . -type f
```

## Find files older than 7 days
```bash
find /tmp -type f -mtime +7
```

## Find files larger than 100MB
```bash
find / -type f -size +100M 2>/dev/null
```

## Execute a command on results
```bash
find . -name "*.log" -exec rm {} \;
```

## Example output
```text
./logs/app.log
./logs/error.log
```

## Notes
- `.` means current directory
- `/` searches from the root (entire system)
- `-name` searches by file name
- `-type f` = files, `-type d` = directories
- `-mtime` filters by modification time
- `-size` filters by file size
- `2>/dev/null` hides permission errors
- `-exec` runs a command on each result

## Common error

### Error message
```bash
find: '/root': Permission denied
```

### Example
![find permission error](/images/find-permission-error.png)

### Cause
You do not have permission to access certain directories.

### Fix
Run with sudo or suppress errors:

```bash
sudo find / -name "file.txt"
```

or

```bash
find / -name "file.txt" 2>/dev/null
```

## Real-world use
- finding log files across a system  
- locating configuration files  
- identifying old files for cleanup  
- searching large directories quickly  

## Screenshot

### Finding log files
![find logs](/images/find-logs.png)

### Finding large files
![find large files](/images/find-size.png)
