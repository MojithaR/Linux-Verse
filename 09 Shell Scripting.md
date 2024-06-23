# Shell Scripting 📜

## Introduction to Shell Scripts 🖥️

- **Shell Scripts**: Scripts written in shell programming languages (e.g., Bash) to automate tasks or execute commands.

## Writing Basic Scripts 📝

- **Script File**: Create a file with a `.sh` extension and include shell commands.

### Example: `hello.sh`
```bash
#!/bin/bash

# Simple script to print a greeting
echo "Hello, World!"
```

## Variables and Control Structures 🛠️

- **Variables**: Store data for use in scripts.
- **Control Structures**: Conditional statements (`if`, `else`, `elif`) and loops (`for`, `while`) control script flow.

### Example: `variables_control.sh`
```bash
#!/bin/bash

# Example script with variables and control structures
name="Alice"
age=30

if [ $age -ge 18 ]; then
    echo "$name is an adult."
else
    echo "$name is a minor."
fi
```

## Script Debugging 🔍

- **Debugging**: Use `echo` statements or debugging tools like `bash -x script.sh` to trace script execution and identify issues.

### Example: Debugging with `echo`
```bash
#!/bin/bash

# Script with debug statements
echo "Starting script..."

# Debugging line
echo "Current directory: $(pwd)"

# Rest of the script...
```

### Summary

Shell scripting allows automation and customization of tasks using shell commands. Basic scripts are created by writing commands in a `.sh` file. Variables and control structures manage data and flow within scripts. Debugging tools like `echo` statements help trace script execution and identify errors, enhancing script reliability and efficiency.
