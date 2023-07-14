```markdown
# 🚀 Sed Commands Cheat Sheet

This cheat sheet demonstrates the usage of GNU sed (stream editor).

## 📝 Basic Usage

```bash
sed 'command' file.txt
```

## 🔄 Text Replacement

```bash
sed 's/old/new/g' file.txt                 # Replaces "old" with "new" on each line.
sed 's/old/new/2' file.txt                 # Replaces the second "old" on each line with "new".
sed 's/old/new/gi' file.txt                # Replaces "old" with "new", ignoring case.
sed 's/\/old/\/new/g' file.txt             # Replaces expressions containing a forward slash (/).
```

## 🗑️ Line Deletion

```bash
sed '4d' file.txt                          # Deletes the fourth line.
sed '2,5d' file.txt                        # Deletes lines from the second to the fifth.
sed '/pattern/d' file.txt                  # Deletes lines containing "pattern".
sed '/pattern/!d' file.txt                 # Deletes lines not containing "pattern".
sed '/^$/d' file.txt                       # Deletes blank lines.
```

## ➕ Line Addition

```bash
sed '2i\New line' file.txt                 # Adds "New line" at the second line.
sed '4a\New line' file.txt                 # Adds "New line" after the fourth line.
```

## 🔄 File Backup

```bash
sed -i.bak 's/old/new/g' file.txt          # Creates a backup file "file.txt.bak" while replacing "old" with "new" in "file.txt".
```

## 🔎 Pattern Matching

```bash
sed '/pattern/!d' file.txt                 # Deletes lines not containing "pattern".
sed '/^$/d' file.txt                       # Deletes blank lines.
```

## 📄 Text Cutting

```bash
sed 's/:/ /g' file.txt                     # Replaces ":" character with a space.
sed -n '2,5p' file.txt                     # Prints lines from the second to the fifth.
```

## 📚 Insert Content From Another File in Place of a Pattern

```bash
sed '/pattern/r file2.txt' file.txt        # Adds the content of "file2.txt" to each line containing "pattern".
```

## 🌈 Conditional Processing

```bash
sed '/pattern/{s/old/new/g}' file.txt      # Replaces "old" with "new" on lines containing "pattern".
```

## 🔄 Using Variables

```bash
sed "s/$var/new_value/g" file.txt          # Replaces the text using a bash variable. (var variable must be defined beforehand)
```

## 🎯 Regular Expressions

```bash
sed '/^begin/,/^end/d' file.txt            # Deletes lines from "begin" to "end".
```

## ➡️ Multiple Edits

```bash
sed -e 's/old/new/g' -e 's/foo/bar/g' file.txt   # Runs multiple `sed` commands on the same line.
```

## 🏷️ Range Indicator

```bash
sed '2,/pattern/d' file.txt                # Deletes lines from the second to "pattern".
```

## 🔢 Line Numbering

```bash
sed '=' file.txt | sed 'N; s/\n/\t/'       # Adds a number at the beginning of each line.
```

## 📝 Text Formatting

```bash
sed -e :a -e 's/^.\{1,79\}$/&;/;ta' file.txt   # Trims each line to up to 79 characters and adds a semicolon at the end.
```

## 💾 Using a Script File

```bash
sed -f scriptfile.sed file.txt             # Applies `sed` operations using a specific script file.
```
```

