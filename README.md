# Promptify

This project provides a utility to flatten the structure of a large project by consolidating the contents of multiple text files into a single output file. The output file is organized in a way that each section corresponds to the content of a specific file within the project, making it easier to process and analyze the data.

### Use this as AI Model Prompting

Developers often face challenges when prompting AI models for their projects because most AI models do not support direct directory structures. Even if some AI models support this feature, they often charge money for it. Additionally, developers frequently need to reference multiple files to ask a question or solve a problem, which can be cumbersome.
This utility addresses these issues by:

- **Consolidating Multiple Files**: By combining multiple text files into a single output file, developers can easily prompt AI models without worrying about directory structures.
- **Cost-Effective Solution**: Since a single text file is supported by any AI model, this utility provides a cost-effective solution for developers.
- **Comprehensive Context**: Including the relative path of each file in the output ensures that the AI model has the necessary context to understand the relationship between different files, improving the accuracy of responses.

## Caution

- **Large Directories**: Avoid running this script on very large directories as it may consume significant resources and take a long time to complete.
- **Content Review**: Always review the content of the generated output file before uploading it to any third-party AI model to ensure that no sensitive or unnecessary information is included.

## Features

- **Flatten Project Structure**: Combines the contents of multiple text files into a single output file.
- **Ignore Patterns**: Supports `.gitignore` and `.promptignore` files to exclude specific files or directories.
- **Text File Detection**: Automatically detects and processes only plain text files.

> The `.promptignore` file is a crucial component of this utility This is similar to the `.gitignore` file used in Git, but it is specific to this utility and should be stored in the root directory of the project being processed.

## Usage

### Command Line

To use this utility, you need to provide the directory path you want to process using the `-dir` flag.

```sh
go run main.go -dir /path/to/your/project
```

If you want to process the current directory, you can use:

```sh
go run main.go
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
go run main.go -dir /path/to/your/project
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

## Installation

1. Clone the repository:

```sh
git clone https://github.com/harrykp/promptify.git
```

2. Navigate to the project directory:

```sh
cd promptify
```

3. Build the project:

```sh
go build
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
