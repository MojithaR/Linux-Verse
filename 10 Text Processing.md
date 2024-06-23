# Text Processing 🔍

## Text Processing Tools 🛠️

| Tool       | Description                                                   |
|------------|---------------------------------------------------------------|
| `grep`     | Searches for patterns in text files.                           |
| `awk`      | Processes and analyzes text files for pattern matching.        |
| `sed`      | Stream editor for filtering and transforming text.             |

## Regular Expressions 🧵

- **Regex**: Patterns used to match and manipulate text based on rules.

## File Redirection and Pipelines 🔄

- **Redirection**: Directs output from a command into files or other commands.
  - Example: `command > output.txt`

- **Pipelines**: Chains commands together, using output of one as input to the next.
  - Example: `command1 | command2`

### Examples
```bash
# Search for a pattern in a file using grep
grep "pattern" filename.txt

# Process and analyze text using awk
awk '{print $1}' filename.txt

# Filter and transform text using sed
sed 's/old_pattern/new_pattern/g' filename.txt

# Redirect output to a file
echo "Hello, World!" > output.txt

# Chain commands using pipelines
cat filename.txt | grep "pattern"
```

### Summary

Text processing in Linux utilizes tools like `grep`, `awk`, and `sed` for searching, processing, and transforming text data. Regular expressions (regex) provide powerful pattern matching capabilities. File redirection (`>`, `>>`) and pipelines (`|`) facilitate efficient handling and manipulation of text output between commands. Mastering these tools enhances productivity and automation in text-based tasks and data processing.
