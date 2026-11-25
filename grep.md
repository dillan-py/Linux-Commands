# Courtesy of ChatGPT: `grep`

The `grep` command is used to search for specific words or patterns inside files.

## Basic Syntax

```bash
grep "WHAT" FILE
```

Let's break that down:

| Component | Meaning |
|---|---|
| `grep` | I want to search for something. |
| `WHAT` | What word or pattern am I looking for? |
| `FILE` | Which file should I search? |

---

## Examples

### Example 1: Search for a specific word

Say, for example, you want to find every line containing the word `failed`:

```bash
grep "failed" auth.log
```

This displays every line in `auth.log` containing the word `failed`.

### Example 2: Ignore uppercase and lowercase

```bash
grep -i "error" system.log
```

The `-i` option ignores case sensitivity.

This also finds:

- `ERROR`
- `Error`
- `error`

### Example 3: Count matching lines

```bash
grep -c "failed" auth.log
```

The `-c` option counts the matching lines.

### Example 4: Show line numbers

```bash
grep -n "failed" auth.log
```

The `-n` option displays the line numbers where matches are found.

### Example 5: Search recursively through directories

```bash
grep -r "failed" /var/log/
```

The `-r` option searches recursively through directories, including files inside subdirectories.

---

## Cheat Sheet

| Option | Meaning |
|---|---|
| `-i` | Ignore uppercase and lowercase |
| `-c` | Count matching lines |
| `-n` | Show line numbers |
| `-r` | Search recursively through directories |

---

## Final Tip

You don't need to memorise every option.

Understand what each building block does, and you can combine them to search through files more effectively.
````
