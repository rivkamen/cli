```markdown
# Code Bundler CLI

This project provides a command-line interface (CLI) tool for bundling code files from a specified list of programming languages into a single file. The bundled file can optionally include comments for the file origin, remove empty lines, and be sorted by name or type.

---

## Features

- **Bundle Command**: Bundles source code files from selected programming languages into one file.
- **Create Response File Command**: Simplifies the usage of the `bundle` command by generating a response file with all necessary options.

---

## Installation

1. Clone the repository or download the source files.
2. Compile the project using your preferred C# development environment (e.g., Visual Studio or Visual Studio Code).
3. Build the project into an executable.

---

## Usage

### `bundle` Command

This command bundles source code files from the current directory into a single file.

#### Options:

- **`--language`** (`-l`)  
  A list of programming languages to include in the bundle (comma-separated).  
  Valid options: `csharp`, `python`, `javascript`, `java`, `html`, `css`, `jsx`, `angular`, or `all` (for all supported languages).  
  **Required**.

- **`--output`** (`-o`)  
  The output file path and name for the bundle.  
  If not provided, the file will be created in the current directory.  
  **Optional**.

- **`--note`** (`-n`)  
  Whether to include the file origin as comments in the bundle.  
  **Optional**.

- **`--sort`** (`-s`)  
  The sorting order for files: either by `name` (default) or by `type`.  
  **Optional**.

- **`--remove-empty-lines`** (`-r`)  
  Whether to remove empty lines from the source files before bundling.  
  **Optional**.

#### Example:

```bash
bundle --output "bundle.txt" --language "python,java" --sort "name" --remove-empty-lines --note
```

### `create-rsp` Command

This command helps users easily generate a response file that can be used with the `bundle` command. The user will be prompted to input the required options, and the command will create a `.rsp` file.

#### Example:

```bash
create-rsp
```

Once the user fills in the necessary details, a `.rsp` file is created. To execute the bundled command later, use the following:

```bash
dotnet @responseFile.rsp
```

---

## Example Workflow:

1. **Generate a Response File**:  
   Run the `create-rsp` command and answer the prompts.
   
2. **Run the `bundle` Command**:  
   Execute the generated `.rsp` file to bundle the files based on the provided options.

---

## How It Works

1. **Language Option**:  
   The `--language` option specifies which programming languages should be bundled. If "all" is selected, all code files in the directory will be included.
   
2. **Output Option**:  
   The `--output` option specifies the file path and name for the output bundle. If left empty, the file is created in the current directory.
   
3. **Note Option**:  
   When the `--note` option is selected, each file’s origin (path) is included as a comment in the bundle, making it easier to trace back the source files.

4. **Sorting Option**:  
   Files can be sorted by `name` (default) or by `type` (file extension). Sorting helps maintain better organization within the bundled file.

5. **Remove Empty Lines Option**:  
   The `--remove-empty-lines` option removes empty lines from the source files before adding them to the bundle.

6. **Creating a Response File**:  
   The `create-rsp` command allows users to answer prompts for all the `bundle` options, which are then saved into a `.rsp` file for easy future use.

---

## Notes:

- **File Paths**: If the output file path contains spaces, it must be enclosed in double quotes.
- **Directory Restrictions**: Files from directories like `bin` and `debug` are automatically excluded from the bundle.

---

## Example of Running the Commands

1. **Bundle Files**:
   ```bash
   bundle --output "C:\Bundles\my_bundle.txt" --language "python,java" --sort "name" --note --remove-empty-lines
   ```

2. **Generate a Response File**:
   ```bash
   create-rsp
   ```

   After providing the necessary input, the response file will be created.

3. **Run the Response File**:
   ```bash
   dotnet @my_bundle_rsp.rsp
   ```

---

## Contribution

Feel free to fork the project, submit issues, and create pull requests. All contributions are welcome!

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

---

### Explanation of Sections:

- **Introduction and Features**: Briefly describes what the project does and its key features.
- **Installation**: Instructions to set up and build the project.
- **Usage**: Detailed instructions on how to use both commands: `bundle` and `create-rsp`.
- **How It Works**: A breakdown of how the key options and commands operate.
- **Example Workflow**: Step-by-step guide on how to use the tool.
- **Notes**: Additional information regarding specific requirements for file paths and directory restrictions.
- **Examples of Running Commands**: Showcasing practical examples of usage.
- **Contribution and License**: Encouraging contributions and providing licensing details.

This layout is user-friendly and provides a clean, clear structure for a README file.
