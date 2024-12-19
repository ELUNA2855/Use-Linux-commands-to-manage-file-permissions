# Linux File Permissions Portfolio

This portfolio demonstrates how to manage file permissions and ownership on a Linux system using various commands.

### Contents:
1. [Viewing File Permissions](01-view-permissions.md)
2. [Changing File Permissions](02-change-permissions.md)
3. [Changing Ownership](03-change-ownership.md)
4. [Special Permissions](04-special-permissions.md)

# 1. Viewing File Permissions in Linux

To see the current permissions of a file or directory, use the `ls -l` command:

```bash
ls -l filename

# Example output
-rwxr-xr-- 1 user group 1234 Dec 19 12:34 filename


#### `02-change-permissions.md`

```markdown
# 2. Changing File Permissions in Linux

Use the `chmod` command to modify file permissions.

### Symbolic Mode:

- Add permission: `+`
- Remove permission: `-`
- Set permission: `=`

```bash
chmod u+x filename  # Add execute permission to user
chmod o-r filename  # Remove read permission from others
chmod g=rx,o=r filename  # Set group to read and execute, others to read-only
Example:
chmod 755 filename  # rwx for owner, rx for group and others





