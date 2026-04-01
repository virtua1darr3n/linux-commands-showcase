# cut, sort, uniq

## What it does
The `cut`, `sort`, and `uniq` commands are used to extract, organise, and filter data from files or command output.

## Scenario
You need to extract specific fields, sort data, and remove duplicates when analysing logs or structured files.

---

## Extract columns with cut

### Extract first column (delimiter = :)
```bash
cut -d: -f1 /etc/passwd
```

---

### Extract multiple fields
```bash
cut -d: -f1,3 /etc/passwd
```

---

## Sort data

### Sort alphabetically
```bash
sort file.txt
```

### Sort in reverse
```bash
sort -r file.txt
```

### Sort numerically
```bash
sort -n numbers.txt
```

---

## Remove duplicates with uniq

### Remove duplicate lines
```bash
uniq file.txt
```

⚠️ Note: input must be sorted first

```bash
sort file.txt | uniq
```

---

### Count duplicate occurrences
```bash
sort file.txt | uniq -c
```

---

## Combine commands (very common)

### Find unique users
```bash
cut -d: -f1 /etc/passwd | sort | uniq
```

---

### Count unique values
```bash
cut -d: -f1 /etc/passwd | sort | uniq -c
```

---

## Notes
- `cut` extracts specific fields  
- `-d` sets delimiter  
- `-f` selects fields  
- `sort` organises output  
- `uniq` removes duplicates  
- `uniq` only works correctly on sorted data  

---

## Common issue

### uniq not removing duplicates
```bash
uniq file.txt
```

### Cause
The file is not sorted.

### Fix
Sort before using uniq:
```bash
sort file.txt | uniq
```

---

## Real-world use
- extracting usernames from system files  
- analysing logs and removing duplicates  
- counting occurrences of events  
- cleaning and organising data  

---

## Screenshot

### Extracting data with cut
![cut output](/images/cut.png)

### Sorting data
![sort output](/images/sort.png)

### Removing duplicates
![uniq output](/images/uniq.png)

### Combined pipeline
![cut sort uniq](/images/cut-sort-uniq.png)
