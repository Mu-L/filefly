# FileFly

FileFly is a Rust command-line utility for handling file and folder operations such as copying, deleting, replacing, and synchronizing. It provides a simple interface to perform these actions with progress tracking and logging capabilities.

## Usage

### Installation

# Windows Installation

Just run the following two commands with Powershell (not CMD)

```shell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
[System.Net.WebClient]::new().DownloadString('https://raw.githubusercontent.com/theprantadutta/filefly/master/install.ps1') | iex
```

# Linux Installation

```shell
curl -L https://github.com/theprantadutta/filefly/raw/master/install.sh | bash
```

To directy use FileFly, make sure you have Rust installed. Then, you can build the project using the following command:

```bash
cargo build --release
```

This will create the executable in the `target/release` directory.

### Commands

FileFly supports the following commands:

#### Copy

Copy a file or folder from the source to the destination.

```bash
filefly copy -s source_path -d destination_path
```

#### Delete

Delete a file or folder.

```bash
filefly delete -f file_or_folder_path
```

#### Replace

Replace a file or folder with another.

```bash
filefly replace -s source_path -d destination_path
```

#### Synchronize

Synchronize a file or folder with another.

```bash
filefly synchronize -s source_path -d destination_path
```

We also support a few flags as well.

1. Disable logging.

```
filefly copy -s source_path -d destination_path --no-log
```

This will work for replace, delete, synchronize as well.

2. Provide Log Level

```
filefly copy -s source_path -d destination_path --log-level=Debug
```

Will accept any of the following
Log level (debug, info, success, warning, error)

This will work for replace, delete, synchronize as well.

## Features

- **Progress Tracking:** FileFly displays progress bars for file operations, keeping you informed about the ongoing tasks.

- **Logging:** The utility provides detailed logging, including success, error, and informational messages.

- **Directory Synchronization:** The synchronize command ensures that the source and destination directories are identical by copying missing files and deleting extraneous ones.

## Examples

### Copy

```bash
filefly copy -s /path/to/source -d /path/to/destination
```

### Delete

```bash
filefly delete -f /path/to/file_or_folder
```

### Replace

```bash
filefly replace -s /path/to/source -d /path/to/destination
```

### Synchronize

```bash
filefly synchronize -s /path/to/source -d /path/to/destination
```

## Contributing

Feel free to contribute to FileFly by opening issues or submitting pull requests. Your feedback and improvements are highly appreciated.

## License

This project is licensed under the Apache License - see the [LICENSE](LICENSE) file for details.
