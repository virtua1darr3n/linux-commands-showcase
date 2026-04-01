# grep

## What it does
The `grep` command searches for specific text or patterns inside files or command output.

## Scenario
You need to search logs for errors, find configuration values, or filter command output during troubleshooting.

---

## Basic search
```bash
grep "error" file.txt
```

---

## Case-insensitive search
```bash
grep -i "error" file.txt
```

---

## Show line numbers
```bash
grep -n "error" file.txt
```

---

## Search multiple files
```bash
grep "error" *.log
```

---

## Search recursively in a directory
```bash
grep -r "error" /var/log
```

---

## Use grep with pipes
```bash
ps aux | grep nginx
```

---

## Notes
- `-i` ignores case  
- `-n` shows line numbers  
- `-r` searches recursively  
- often used with pipelines for filtering  

---

## Common issue

### No results returned
```bash
grep "error" file.txt
```

### Cause
- the text does not exist  
- case mismatch  

### Fix
Use case-insensitive search:
```bash
grep -i "error" file.txt
```

---

## Real-world use
- searching logs for errors  
- finding failed login attempts  
- locating configuration values  
- filtering command output  

---

## Screenshot

### Searching a file
![grep basic](/images/grep-basic.png)

### Searching logs
![grep logs](/images/grep-logs.png)

### Filtering processes
![grep process](/images/grep-ps.png)
