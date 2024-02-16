# 03-Create, Delete, Copy, and Move Files and Directories

To effectively combine the detailed explanations with simulated outputs for a comprehensive understanding of basic Linux commands, we'll maintain a focus on clarity and relevance, avoiding redundancy in simulated outputs.

## Understanding Basic Linux Commands with Simulated Outputs

1. **Creating Directories: `mkdir`**
   - **Use:** Creates a new directory.
   - **Command:** `mkdir /home/raja`
   - **Expected Result:** A new directory named `raja` is created under `/home`.

2. **Creating Files: `touch`**
   - **Use:** Creates a new file or updates the timestamp of an existing file.
   - **Command:** `touch /home/raja/Documents/Invoice.pdf`
   - **Expected Result:** A file named `Invoice.pdf` appears in `/home/raja/Documents`.

3. **Copying Files: `cp`**
   - **Use:** Copies files from one location to another.
   - **Command:** `cp /home/raja/Documents/Invoice.pdf /home/david/`
   - **Expected Result:** `Invoice.pdf` is duplicated into `/home/david`.

4. **Removing Files: `rm`**
   - **Use:** Deletes files.
   - **Command:** `rm /home/raja/Documents/Invoice.pdf`
   - **Expected Result:** `Invoice.pdf` is removed from `/home/raja/Documents`.

5. **Moving/Renaming Files: `mv`**
   - **Use:** Moves or renames files and directories.
   - **Command:** `mv /home/david/Invoice.pdf /home/david/Invoice_Old.pdf`
   - **Expected Result:** `Invoice.pdf` in `/home/david` is renamed to `Invoice_Old.pdf`.

## Detailed Listing and Hidden Files

- **Command:** `ls -al /home/raja`
- **Simulated Output:**
  ```
  total 12
  drwxr-xr-x  3 raja raja 4096 Oct  7 12:00 .
  drwxr-xr-x  4 root root 4096 Oct  7 11:57 ..
  drwxr-xr-x  2 raja raja 4096 Oct  7 12:01 Documents
  ```
- **Explanation:** Shows all files (including hidden) in `/home/raja` in a detailed format, including permissions, owner, and size.

## Navigating Directories

- **Understanding Paths:** Use `cd` to change directories, utilizing absolute or relative paths. `cd /` takes you to the root, while `cd ..` moves up one directory level.

## Copying Directories: `cp -r`

- **Use:** Recursively copies directories.
- **Command:** `cp -r /home/raja /home/backup_raja`
- **Expected Result:** A complete copy of `/home/raja` is created at `/home/backup_raja`.

## Viewing Current Directory: `pwd`

- **Use:** Displays the current working directory.
- **Running `pwd` in `/home/raja` gives:**
  ```
  /home/raja
  ```

Each command is highly useful for day-to-day operations on a Linux system, and understanding their outputs helps in verifying operations and troubleshooting.
