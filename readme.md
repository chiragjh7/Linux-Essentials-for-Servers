# Linux Essentials Commands for Servers

This document serves as a quick reference guide for essential Linux commands commonly used on servers. These commands are powerful tools for managing files, processes, networking, and system administration tasks.

## Table of Contents

1. [grep](#grep)
2. [tail](#tail)
3. [curl](#curl)
4. [nc (netcat)](#nc-netcat)
5. [less](#less)
6. [more](#more)

---

## grep

`grep` is a command-line utility for searching plain-text data sets for lines that match a regular expression.

Usage:
```bash
grep [options] pattern [file...]
```
### Additional Options:
- `-r`: Recursively search subdirectories.
- `-l`: Print only the names of files containing matches.
- `-c`: Print only a count of matching lines per file.
- `-A <num>`: Print <num> lines of trailing context after matching lines.
- `-B <num>`: Print <num> lines of leading context before matching lines.
- `-E`: Interpret pattern as an extended regular expression.

These additional options provide more flexibility and control over how `grep` searches and displays matching lines. For example:

```bash
grep -r "pattern" /path/to/directory
grep -l "pattern" /path/to/directory/*.txt
grep -c "pattern" /path/to/file
```
---

## tail

`tail` is a command-line utility used to display the last few lines of a file.

Usage:
```bash
tail [options] [file...]
```
### Options:
- `-n <number>`: Output the last <number> lines, instead of the last 10.
- `-f`: Output appended data as the file grows.

Example:
```bash
tail -f /opt/logs/sample.log
```
---
## curl

`curl` is a command-line tool for transferring data with URL syntax.

Usage:
```bash
curl [options] [URL...]
```
### Options:
- `-O`: Write output to a local file named like the remote file.
- `-L`: Follow redirects.
- `-s`: Silent mode. Don't show progress meter or error messages.
- `-I`: Fetch the HTTP-header only.
- `-X <method>`: Specifies a custom request method to use when communicating with the HTTP server.
- `-H <header>`: Pass additional HTTP headers.
- `-d <data>`: Sends the specified data in a POST request.
- `-vvv`: Verbose mode. Show detailed information including protocol data sent and received.

Example:
```bash
curl -vvv https://example.com
```
---
## nc (netcat)

`nc`, also known as netcat, is a versatile networking tool used for reading from and writing to network connections using TCP or UDP.

Usage (listening mode):
```bash
nc -l -p [port]
```
Usage (client mode):
```bash
nc [hostname/IP] [port]
```

### Options:
- `-l`: Used for listening mode, for inbound connections.
- `-p <port>`: Specify the port number to listen on or connect to.
- `-v`: Verbose mode. Display more information about the connection.
- `-z`: Zero-I/O mode. Used for scanning purposes to see if a port is open without sending any data.
- `-n`: Do not do any DNS or service lookups, which can speed up operations.

Example (listening mode):
```bash
nc -l -p 1234
```
Example (client mode):
```bash
nc -vz localhost 1234
```

## less

`less` is a command-line utility for viewing text files with paging.

Usage:
```bash
less [options] [file...]
```
### Options:
- -N: Display line numbers.
- `-i`: Ignore case when searching.
- `-S`: Chop long lines instead of wrapping.
- `-F`: Quit immediately if the entire file can be displayed on one screen.
- `-R`: Raw control characters are displayed, and the terminal will not be reset when less exits.
---
## more

`more` is a command-line utility similar to `less`, used for viewing text files one page at a time.

Usage:
```bash
more [options] [file...]
```
### Options:
- `-c`: Clear the screen before displaying the next page.
- `-p`: Don't scroll. Instead, clear the screen and display the text.
- `-d`: Display help message showing available commands.
- `-l`: Ignore form feeds (^L) in the input.
- `-s`: Squeeze multiple blank lines into one.