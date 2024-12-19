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
# Example:
chmod 755 filename  # rwx for owner, rx for group and others


#### `03-change-ownership.md`

```markdown
# 3. Changing File Ownership in Linux

Use the `chown` and `chgrp` commands to change file ownership.

### `chown` Command:

```bash
chown user1 filename  # Change owner to user1
chown user1:group1 filename  # Change owner to user1 and group to group1
chown :group1 filename  # Change only the group to group1

chgrp group1 filename  # Change the group of the file to group1


#### `04-special-permissions.md`

```markdown
# 4. Special Permissions in Linux

Linux supports several special file permissions:

### Setuid (`s`):
When set on an executable, the program runs with the permissions of the file owner.

```bash
chmod u+s filename  # Add setuid to a file

chmod g+s directory_name  # Set setgid on a directory





