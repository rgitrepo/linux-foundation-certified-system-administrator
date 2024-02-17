# M16 Use Input-Output Redirection in Linux

Hello, Linux explorers! Today's session is dedicated to the powerful concept of input and output redirection. This feature of Linux shell commands allows you to direct the output of commands to files, input from files to commands, and even shuffle error messages around. Let's get started with practical examples and explanations.

## Understanding Redirection

In Linux, when we run commands, they typically read input (`stdin`), write output (`stdout`), or write error messages (`stderr`). By default, `stdin` reads from the keyboard, `stdout` and `stderr` are displayed on the screen. Redirection operators change these defaults.

### Redirecting Output to a File

- **Overwriting Content**:

  ```bash
  $ date > file.txt
  ```
  Each time you run this, `file.txt` will contain the latest date and time, overwriting the previous content.

- **Appending Content**:

  ```bash
  $ date >> file.txt
  ```
  Each time you run this, the new date and time are added to `file.txt`, preserving existing content.

### Redirecting `stdout` and `stderr`

- **Separately Redirecting**:

  ```bash
  $ grep -r '^The' /etc/ > output.txt 2> errors.txt
  ```
  Standard output (`stdout`) goes to `output.txt`, errors (`stderr`) go to `errors.txt`.

- **Redirecting Both to the Same File**:

  ```bash
  $ grep -r '^The' /etc/ > all_output.txt 2>&1
  ```
  Both output and errors are directed to `all_output.txt`.

### Redirecting Input from a File

```bash
$ sendemail someone@example.com < emailcontent.txt
```
Sends an email with the content of `emailcontent.txt` as the message body.

### Using Here Documents and Here Strings

- **Here Document**:

  ```bash
  $ sort <<EOF
  > 6
  > 3
  > 2
  > 5
  > 1
  > 4
  > EOF
  ```
  Sorts the numbers listed and outputs them in sorted order.

- **Here String**:

  ```bash
  $ bc <<<"1+2+3+4"
  ```
  Performs the calculation and outputs `10`.

## Practical Usage of Redirection

### Silent Operation

To run `grep` silently, without permission denied errors cluttering the screen:

```bash
$ grep -r '^The' /etc/ 2>/dev/null
```

### Organizing Output

To sort and format the non-comment lines of `/etc/login.defs`:

```bash
$ grep -v '^#' /etc/login.defs | sort | column -t
```

Outputs a neatly formatted table of configuration settings.

### Backing Up and Redirecting

If you want to backup the current `stdout` and `stderr`:

```bash
$ exec 3>&1 4>&2
$ grep -r '^The' /etc/ 1>all_output.txt 2>&1
```

This will redirect all output to `all_output.txt`, while file descriptors 3 and 4 can be used to restore the original `stdout` and `stderr`.

### Conclusion

Input and output redirection are fundamental tools in the Linux command-line environment. They give you control over where your command's input comes from and where its output goes, including error messages. With these commands, you can create logs, manage files, automate email sending, and much more. Remember to use redirection thoughtfully, as it can overwrite important data. Happy redirection!