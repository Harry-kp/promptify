# Promptify

https://github.com/user-attachments/assets/11bd8c58-1247-45fa-adb4-f7d4290f9140

This project provides a utility to flatten the structure of a large project by consolidating the contents of multiple text files into a single output file. The output file is organized in a way that each section corresponds to the content of a specific file within the project, making it easier to process and analyze the data.

### Use this as AI Model Prompting

Developers often face challenges when prompting AI models for their projects because most AI models do not support direct directory structures. Even if some AI models support this feature, they often charge money for it. Additionally, developers frequently need to reference multiple files to ask a question or solve a problem, which can be cumbersome.

## Caution

- **Large Directories**: Avoid running this script on very large directories as it may consume significant resources and take a long time to complete.
- **Content Review**: Always review the content of the generated output file before uploading it to any third-party AI model to ensure that no sensitive or unnecessary information is included.

## Features

- **Flatten Project Structure**: Combines the contents of multiple text files into a single output file.
- **Ignore Patterns**: Supports `.gitignore` and `.promptignore` files to exclude specific files or directories.
- **Text File Detection**: Automatically detects and processes only plain text files.

> The `.promptignore` file is a crucial component of this utility This is similar to the `.gitignore` file used in Git, but it is specific to this utility and should be stored in the root directory of the project being processed.

## Installation

### Prerequisites

Ensure you have the following installed on your system:

- [Go](https://golang.org/doc/install) (version 1.16 or later)

### Steps

1. **Download the latest release**

   You can download the latest release from our [Releases Page](https://github.com/Harry-kp/promptify/releases). Choose the appropriate binary for your operating system.

2. **Install the binary**

   After downloading the tar.gz file, extract the contents and navigate to the extracted directory.Now,
   you need to make file executable and move it to a directory included in your system's `PATH`.

   For Linux and macOS:

   ```sh
   chmod +x promptify
   mv promptify /usr/local/bin/
   ```

   For Windows:

   - Move the file to a directory included in your system's `PATH`.

## Usage

### Command Line

To use this utility, you need to provide the directory path you want to process using the `-dir` flag.

```sh
promptify -dir /path/to/your/project
```

If you want to process the current directory, you can use:

```sh
promptify
```

### Output

The output will be written to a file named after the directory being processed, with a `.txt` extension. For example, if you process a directory named `project`, the output file will be named `project.txt`.

### Example

Given the following directory structure:

```
/path/to/your/project
├── file1.txt
├── file2.txt
├── .gitignore
└── subdir
    └── file3.txt
```

Running the command:

```sh
promptify -dir /path/to/your/project
```

Will produce an output file named `project.txt` with the following content:

```
-------------------------------file1.txt-------------------------------
Content of file 1...
-------------------------------file2.txt-------------------------------
Content of file 2...
-------------------------------subdir/file3.txt-------------------------------
Content of file 3...
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
