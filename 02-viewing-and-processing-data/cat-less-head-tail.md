# Viewing File Contents

## What it does
The `cat`, `less`, `head`, and `tail` commands are used to view and inspect file contents in Linux.

## Scenario
You need to quickly read logs, inspect configuration files, or view large files without opening a GUI editor.

---

## View entire file
```bash
cat file.txt
```

---

## View large files (scrollable)
```bash
less file.txt
```

### Useful controls
- `q` → quit  
- `/text` → search  
- `n` → next match  

---

## View first lines of a file
```bash
head file.txt
```

### Show first 10 lines (default)
```bash
head file.txt
```

### Show first 20 lines
```bash
head -n 20 file.txt
```

---

## View last lines of a file
```bash
tail file.txt
```

### Show last 10 lines (default)
```bash
tail file.txt
```

### Show last 20 lines
```bash
tail -n 20 file.txt
```

---

## Monitor logs in real time
```bash
tail -f /var/log/syslog
```

---

## Example output
```text
INFO: Service started
ERROR: Failed to connect
WARNING: Retry attempt
```

---

## Notes
- `cat` is best for small files  
- `less` is ideal for large files  
- `head` shows the beginning of files  
- `tail` shows the end of files  
- `tail -f` is commonly used for live log monitoring  

---

## Common issue

### File not found
```bash
cat file.txt
```

### Error
```bash
cat: file.txt: No such file or directory
```

### Cause
The file does not exist in the current directory.

### Fix
Check location:
```bash
pwd
ls -l
```

---

## Real-world use
- viewing log files  
- checking configuration files  
- monitoring live system logs  
- quickly inspecting file contents  

---

## Screenshot

### Viewing file with cat
![cat output](/images/cat.png)

### Viewing file with less
![less output](/images/less.png)

### Using head and tail
![head tail](/images/head-tail.png)

### Monitoring logs
![tail follow](/images/tail-f.png)
