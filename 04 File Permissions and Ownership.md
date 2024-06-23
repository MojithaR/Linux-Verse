# 🔒 File Permissions and Ownership

Understanding file permissions and ownership in Unix-like systems is crucial for managing security and access control.

## Permissions Overview

Permissions determine who can read, write, and execute files and directories.

### Types of Permissions

| Symbol | Permission       | Description                                         |
|--------|------------------|-----------------------------------------------------|
| `r`    | Read             | Allows reading and listing files in a directory.    |
| `w`    | Write            | Allows modifying and deleting files in a directory. |
| `x`    | Execute          | Allows executing files or traversing directories.   |

### Special Permissions

Some special permissions include:

- **Setuid (`s`) and Setgid (`g`)**: Executes a file with the permissions of the file owner/group.
- **Sticky Bit (`t`)**: Only the file owner can delete or rename the file within a directory.

## Changing Permissions

Permissions can be changed using the `chmod` command.

```bash
# Example: Give read, write, and execute permissions to the owner of a file
chmod u+rwx filename
