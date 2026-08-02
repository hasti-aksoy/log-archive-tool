# Log Archive Tool

A simple Bash CLI tool that compresses log directories into timestamped `.tar.gz` archives.

## Project URL

https://roadmap.sh/projects/log-archive-tool 


## Features

* Accepts a log directory as a command-line argument
* Validates the provided directory
* Compresses logs using `tar` and `gzip`
* Adds the date and time to each archive filename
* Stores archives in `~/log-archives`
* Records successful archive operations in `archive.log`
* Can be executed globally as `log-archive`

## Usage

```bash
log-archive <log-directory>
```

Example:

```bash
log-archive /var/log
```

Or with a test directory:

```bash
log-archive ~/test-logs
```

## Example Output

```text
Creating archive...
Archive created successfully:
/home/user/log-archives/logs_archive_20260802_183246.tar.gz
```

## Archive Log

Successful operations are recorded in:

```text
~/log-archives/archive.log
```

Example:

```text
[2026-08-02 18:32:46] Source: /home/user/test-logs | Archive: /home/user/log-archives/logs_archive_20260802_183246.tar.gz
```

## Installation

Make the script executable:

```bash
chmod +x log-archive
```

Create a symbolic link:

```bash
sudo ln -s "$(realpath log-archive)" /usr/local/bin/log-archive
```

After installation, the command can be executed from anywhere:

```bash
log-archive ~/test-logs
```

## Requirements

* Linux or another Unix-based operating system
* Bash
* `tar`
* `gzip`
