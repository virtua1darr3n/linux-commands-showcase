# cd

## What it does
The `cd` (change directory) command is used to navigate between directories in the filesystem.

## Scenario
You need to move between directories to access files, logs, or configuration folders while working on a system.

## Basic Usage
```bash
cd directory-name
```

## Go into a directory
```bash
cd Documents
```

## Go up one level
```bash
cd ..
```

## Go to home directory
```bash
cd ~
```

## Go to previous directory
```bash
cd -
```

## Use absolute path
```bash
cd /var/log
```

## Use relative path
```bash
cd ../Downloads
```

## Notes
- `cd ..` moves up one directory
- `cd ~` returns to your home directory
- `cd -` switches to the previous directory
- absolute paths start from `/`
- relative paths depend on your current location

## Screenshot

### Changing directories
![cd command](/images/cd-basic.png)

### Moving to parent directory
![cd parent](/images/cd-parent.png)
