<h1>JWipe - Disk Sanitization</h1>

<h2>Description</h2>
This guide explains how to manage file permissions in Linux using a series of commands. Linux file permissions control access to files and directories, ensuring security and proper management of resources. The following steps provide a detailed process for listing, modifying, and setting file permissions, changing file ownership, and more advanced permission settings.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 
- <b>Linux</b>

<h2>Environments Used </h2>

- <b>Windows 10or11</b> (21H2)

<h2>Program walk-through:</h2>

Step 1: List File Permissions (ls -l)

To view the current permissions of a file, use the `ls -l` command:

ls -l filename

Example:
ls -l myfile.txt
Output:
-rwxr-xr-- 1 john staff 1234 Dec 19 12:34 myfile.txt

Here, the permissions are shown as `rwxr-xr--`:
- Owner (john): Read, write, execute (rwx)
- Group (staff): Read, execute (r-x)
- Others: Read only (r--)

---

Step 2: Modify File Permissions (chmod)

Now, let's change the file's permissions. There are two main methods: symbolic and numeric.

Using Symbolic Mode

Example 1: Add execute permission for the owner:
chmod u+x myfile.txt

Example 2: Remove write permission from the group:
chmod g-w myfile.txt

Example 3: Set read-only permissions for others:
chmod o=r myfile.txt

Using Numeric Mode

Permissions can also be set using numbers. Here's how to interpret them:
- `4` = Read (r)
- `2` = Write (w)
- `1` = Execute (x)

To set permissions for owner (rwx), group (r-x), and others (r--):
chmod 755 myfile.txt

This grants:
- Owner: read, write, execute (rwx)
- Group: read, execute (r-x)
- Others: read only (r--)

---

Step 3: Change File Owner (chown)

If you need to change the owner or group of a file, use the `chown` command.

Example 1: Change the owner of the file to `alice`:
chown alice myfile.txt

Example 2: Change both the owner to `alice` and the group to `admins`:
chown alice:admins myfile.txt

---

Step 4: Change Group Ownership (chgrp)

If you just need to modify the group ownership, use `chgrp`.

Example: Change the group of the file to `admin`:
chgrp admin myfile.txt

---

Step 5: Set Default File Permissions (umask)

`umask` defines the default permissions when you create new files. For instance, if you set `umask 022`, files will have default permissions of `rw-r--r--` (read and write for the owner, and read for others).

Example: Set the default permissions for files:
umask 022

---

Step 6: Set Access Control Lists (ACLs) (setfacl and getfacl)

ACLs provide finer control over permissions for users and groups.

Example 1: Give `john` read and write permissions:
setfacl -m u:john:rw myfile.txt

Example 2: View the ACLs of a file:
getfacl myfile.txt

---

Step 7: Change Permissions Recursively Using `find`

To apply changes to multiple files at once, use `find` with `chmod`, `chown`, or `chgrp`.

Example: Change permissions for all `.txt` files in the current directory:
find . -name "*.txt" -exec chmod 644 {} \;

This sets permissions for all `.txt` files to `rw-r--r--`.

---

Summary of Commands in Real-World Scenarios:

1. List permissions:
   ls -l filename

2. Modify permissions:
   - Add execute for owner: chmod u+x filename
   - Remove write for group: chmod g-w filename
   - Set read-only for others: chmod o=r filename
   - Numeric example: chmod 755 filename

3. Change owner/group:
   - Change owner: chown user filename
   - Change owner and group: chown user:group filename

4. Change group ownership:
   chgrp group filename

5. Set default permissions:
   umask 022

6. Set and view ACLs:
   - Set ACL for user: setfacl -m u:username:rw filename
   - View ACL: getfacl filename

7. Change permissions recursively:
   find . -name "*.txt" -exec chmod 644 {} \;

---

This step-by-step process will help you efficiently manage file permissions on your Linux syste
