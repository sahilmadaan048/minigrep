# minigrep

minigrep is a simple command-line utility written in Rust that replicates the basic functionality of the traditional `grep` tool. It allows users to search for a specified query within a file and displays the lines containing that query.

## Features

- **Case-sensitive search**: By default, the search is case-sensitive.
- **Case-insensitive search**: Optionally, perform case-insensitive searches by setting an environment variable.

## Usage

```bash
cargo run <QUERY> <FILE_PATH>
```

- `<QUERY>`: The string to search for.
- `<FILE_PATH>`: The path to the file in which to search.

### Example

Given a file `poem.txt`:

```
The quick brown fox
jumps over the lazy dog.
Duct tape is useful.
```

To search for the word "duct" in a case-sensitive manner:

```bash
cargo run duct poem.txt
```

Output:

```
Duct tape is useful.
```

To perform a case-insensitive search, set the `CASE_INSENSITIVE` environment variable:

```bash
CASE_INSENSITIVE=1 cargo run duct poem.txt
```

Output:

```
Duct tape is useful.
```

## Implementation Details

The minigrep project is structured as follows:

- **Command-line arguments**: The program accepts two positional arguments: the query and the file path.
- **Environment variable**: The `CASE_INSENSITIVE` environment variable determines if the search should be case-insensitive.
- **Error handling**: The program includes basic error handling for scenarios such as missing arguments or file access issues.

For a detailed walkthrough of building a similar tool in Rust, refer to Chapter 12 of "The Rust Programming Language" book.

## License

This project is licensed under the MIT License. 
