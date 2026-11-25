// Courtesy of ChatGPT: `find`

The `find` command is used to search for files and directories on a Linux system.

## Basic Syntax

```bash
find WHERE -name WHAT
```

Let's break that down:

| Component | Meaning |
|---|---|
| `find` | I want to find something. |
| `WHERE` | Where should I search (`/path`)? |
| `-name` | What is the name of the thing? |
| `WHAT` | What am I looking for? |

---

## Examples

### Example 1: Find a specific file

```bash
find /home/user -name "notes.txt"
```

### Example 2: Find all log files

```bash
find / -name "*.log"
```

### Example 3: Search everywhere inside a directory

```bash
find /home/user/Documents -type f
```

Here:

- `-type f` means only files.
- `-type d` means only directories.

Or, for example:

```bash
find /home/user -type d
```

---

## Cheat Sheet

| Command | Meaning |
|---|---|
| `find .` | Search current directory |
| `find /home` | Search in `/home` |
| `-name "*.txt"` | Find text files |
| `-iname "*.txt"` | Find text files, ignoring case sensitivity |
| `-type f` | Files only |
| `-type d` | Directories only |
| `-size +10M` | Larger than 10 MB |
| `-mtime -7` | Modified within the last 7 days |

---

## Final Tip

Notice that you don't need to memorise everything.

You just need to understand what each building block does.
