# grep (Advanced)

## What it does
Advanced `grep` usage allows for powerful pattern matching, filtering, and log analysis using regular expressions and additional options.

## Scenario
You are analysing logs, filtering specific patterns, excluding noise, or extracting useful data during troubleshooting.

---

## Exclude results
```bash
grep -v "INFO" app.log
```

---

## Match whole words only
```bash
grep -w "error" app.log
```

---

## Show lines before and after match
```bash
grep -C 2 "error" app.log
```

### Before only
```bash
grep -B 2 "error" app.log
```

### After only
```bash
grep -A 2 "error" app.log
```

---

## Count matches
```bash
grep -c "error" app.log
```

---

## Show only matching text
```bash
grep -o "error" app.log
```

---

## Use regular expressions

### Match lines starting with a word
```bash
grep "^ERROR" app.log
```

### Match lines ending with a word
```bash
grep "failed$" app.log
```

### Match multiple patterns
```bash
grep -E "ERROR|WARNING" app.log
```

---

## Search multiple files with line numbers
```bash
grep -rn "error" /var/log
```

---

## Ignore binary files
```bash
grep -I "error" *
```

---

## Notes
- `-v` excludes matches  
- `-w` matches whole words  
- `-C`, `-A`, `-B` show context  
- `-c` counts matches  
- `-o` outputs only matched text  
- `-E` enables extended regex  
- `^` = start of line  
- `$` = end of line  

---

## Common issue

### Too many results
```bash
grep "error" /var/log/*
```

### Cause
Searching without filters returns excessive output.

### Fix
Use filters or refine search:
```bash
grep -i "error" /var/log/syslog
```

or:
```bash
grep -r "error" /var/log | head
```

---

## Real-world use
- analysing logs with context around errors  
- filtering out noise (e.g. removing INFO logs)  
- counting occurrences of events  
- extracting specific patterns from logs  
- identifying failures across multiple files  

---

## Screenshot

### Excluding results
![grep exclude](/images/grep-v.png)

### Context lines
![grep context](/images/grep-context.png)

### Regex matching
![grep regex](/images/grep-regex.png)

### Counting matches
![grep count](/images/grep-count.png)
