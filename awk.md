The `awk` command is used to read, process, filter and display information from files.

Think of `awk` as a tool that reads information in columns.

It is particularly useful when working with structured text files, logs and command output.

## Understanding the Basics

Imagine you have a file called `users.txt`:

```text
John 25 London
Sarah 30 Birmingham
David 22 Manchester
James 28 Leeds
```

Each line contains three columns:

| Column | Information |
|---|---|
| Column 1 | Name |
| Column 2 | Age |
| Column 3 | City |

Now suppose you only want to display the names.

```bash
awk '{print $1}' users.txt
```

Output:

```text
John
Sarah
David
James
```

### What is happening?

Let's break it down:

| Component | Meaning |
|---|---|
| `awk` | Start using awk. |
| `{ }` | Instructions for awk. |
| `print` | Display something. |
| `$1` | First column. |
| `users.txt` | The file to read. |

---

## Understanding the Dollar Signs

One of the most important things to understand about `awk` is how it identifies columns.

| Expression | Meaning |
|---|---|
| `$0` | Entire line |
| `$1` | First column |
| `$2` | Second column |
| `$3` | Third column |
| `$NF` | Last column |
| `NF` | Number of columns |

### Example 1: Display the entire line

```bash
awk '{print $0}' users.txt
```

Displays every complete line.

### Example 2: Display the second column

```bash
awk '{print $2}' users.txt
```

Output:

```text
25
30
22
28
```

### Example 3: Display the last column

```bash
awk '{print $NF}' users.txt
```

Output:

```text
London
Birmingham
Manchester
Leeds
```

Notice that `$NF` automatically selects the last column, regardless of how many columns there are.

### Example 4: Display the number of columns

```bash
awk '{print NF}' users.txt
```

Output:

```text
3
3
3
3
```

Each line contains three columns.

---

## Understanding the Basic Structure

This is the basic structure of `awk`:

```bash
awk 'CONDITION {ACTION}' filename
```

Think of it like this:

"If this condition is true, perform this action."

For example:

- `CONDITION` = What am I looking for?
- `ACTION` = What should awk do when it finds it?

This is probably the most important concept to understand about `awk`.

---

## Filtering Information

This is where `awk` becomes particularly useful.

Suppose you only want to find users older than 25.

```bash
awk '$2 > 25 {print $1}' users.txt
```

Output:

```text
Sarah
James
```

Let's break it down:

| Component | Meaning |
|---|---|
| `$2` | Look at the second column (age). |
| `> 25` | Check whether the age is greater than 25. |
| `{print $1}` | Display the first column (name). |

Only Sarah and James meet the condition.

### More Filtering Examples

**Find users younger than 25:**

```bash
awk '$2 < 25 {print $1}' users.txt
```

**Find users aged exactly 25:**

```bash
awk '$2 == 25 {print $1}' users.txt
```

**Find users aged 25 or older:**

```bash
awk '$2 >= 25 {print $1}' users.txt
```

**Display names and cities for users older than 25:**

```bash
awk '$2 > 25 {print $1, $3}' users.txt
```

Output:

```text
Sarah Birmingham
James Leeds
```

---

## Understanding Comparison Operators

These operators allow you to filter information.

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

You can use these operators inside your `awk` conditions.

---

## Useful awk Commands

| Command | Meaning |
|---|---|
| `awk '{print $1}' file` | Display the first column |
| `awk '{print $2}' file` | Display the second column |
| `awk '{print $NF}' file` | Display the last column |
| `awk '{print $0}' file` | Display the entire line |
| `awk '{print NF}' file` | Display the number of columns |
| `awk '$2 > 25' file` | Display lines where column 2 is greater than 25 |
| `awk '$2 == 25' file` | Display lines where column 2 equals 25 |
| `awk '{print $1, $3}' file` | Display columns 1 and 3 |

---

## Bonus: Understanding Field Separators

By default, `awk` separates columns using whitespace (spaces or tabs).

But what happens if your file uses commas instead?

Imagine a CSV file called `users.csv`:

```text
John,25,London
Sarah,30,Birmingham
David,22,Manchester
James,28,Leeds
```

You can tell `awk` to use commas as the separator with `-F`:

```bash
awk -F ',' '{print $1}' users.csv
```

Output:

```text
John
Sarah
David
James
```

Here:

- `-F` specifies the field separator.
- `','` tells awk to separate columns using commas.

You can also use a colon:

```bash
awk -F ':' '{print $1}' /etc/passwd
```

This is particularly useful when examining Linux system files.

---

## Final Tip

Don't think of `awk` as a complicated programming language.

Think of it as a tool that allows you to:

1. Read information in columns.
2. Select specific columns.
3. Filter information using conditions.
4. Display only the information you need.

Once you understand `$1`, `$2`, `$NF` and the basic `CONDITION {ACTION}` structure, you've already learned the foundations of `awk`.

**Remember:**

`grep` helps you find matching lines.

`awk` helps you extract and process information within those lines.

-- Courtesy of ChatGPT: `awk`

