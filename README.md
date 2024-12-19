# Linux File Permissions Portfolio

This repository showcases how to manage **Linux file permissions**, **ownership**, and **special permissions** using the command line. It provides detailed examples, syntax, and explanations to help users understand file and directory management in a Linux environment.

### 📚 Table of Contents
1. [Viewing File Permissions](01-view-permissions.md)
2. [Changing File Permissions](02-change-permissions.md)
3. [Changing Ownership](03-change-ownership.md)
4. [Special Permissions](04-special-permissions.md)
5. [Best Practices in File Permissions](05-best-practices.md)

---

## 🚀 Introduction

Managing file permissions effectively is crucial for maintaining security and ensuring that files are accessible only to the intended users. In this portfolio, you'll learn:

- How to **view**, **modify**, and **manage** file permissions.
- How to change **ownership** and **group ownership** of files.
- The **special permissions** (Setuid, Setgid, Sticky Bit) used to manage executable files and directories.

# 1. Viewing File Permissions in Linux

To view the current file or directory permissions, use the `ls -l` command. It displays the permissions, ownership, and other metadata of files.

```bash
ls -l filename
