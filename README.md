# BalkanShell
A custom Unix shell implementation inspired by Bash, developed as part of the 42 School curriculum. BalkanShell provides a command-line interface with support for executing commands, managing environment variables, handling pipes, redirections, and built-in commands.
## Features
- Command execution with arguments
- Environment variable management
- Input/output redirection (`>`, `>>`, `<`)
- Pipe support (`|`) for command chaining
- Heredoc functionality (`<<`)
- Signal handling (Ctrl+C, Ctrl+D)
- Quote handling (single and double quotes)
- Built-in commands:
  - `echo`: Display a line of text
  - `cd`: Change directory
  - `pwd`: Print working directory
  - `export`: Set environment variables
  - `unset`: Remove environment variables
  - `env`: Display environment variables
  - `exit`: Exit the shell
## Prerequisites
To build and run BalkanShell, you need:
- GCC or another C compiler
- GNU Make
- Readline library
- A Unix-like operating system (Linux, macOS)
## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/balkanshell.git
   cd balkanshell
   ```
2. Install the readline library (if not already installed):
   - On Ubuntu/Debian:
     ```bash
     sudo apt-get install libreadline-dev
     ```
   - On macOS (using Homebrew):
     ```bash
     brew install readline
     ```
3. Compile the project:
   ```bash
   make
   ```
4. Run the shell:
   ```bash
   ./minishell
   ```
## Usage Examples
### Basic Command Execution
```bash
balkanshell$ ls -la
balkanshell$ grep "pattern" file.txt
balkanshell$ cat file.txt | grep "pattern"
```
### Environment Variables
```bash
balkanshell$ export NAME=value
balkanshell$ echo $NAME
value
balkanshell$ env
# Displays all environment variables
balkanshell$ unset NAME
```
### Redirections
```bash
# Output redirection
balkanshell$ ls > output.txt
balkanshell$ ls >> output.txt  # Append
# Input redirection
balkanshell$ cat < input.txt
# Heredoc
balkanshell$ cat << EOF
> Type your text here
> More text
> EOF
```
### Pipes
```bash
balkanshell$ ls -la | grep ".c" | wc -l
```
### Built-in Commands
```bash
# Change directory
balkanshell$ cd /path/to/directory
balkanshell$ cd ..
balkanshell$ cd ~
# Print working directory
balkanshell$ pwd
# Exit the shell
balkanshell$ exit
```
## Project Structure
```
.
├── includes/            # Header files
│   ├── builtin.h        # Built-in command declarations
│   ├── lexer.h          # Lexical analyzer definitions
│   ├── minishell.h      # Main header with data structures
│   └── parser.h         # Parser definitions
├── libft/               # Custom C library
├── srcs/                # Source files
│   ├── builtin/         # Built-in command implementations
│   ├── environ/         # Environment variable handling
│   ├── exec/            # Command execution
│   ├── free/            # Memory management
│   ├── heredoc/         # Heredoc functionality
│   ├── lexer/           # Lexical analyzer
│   ├── parser/          # Command parser
│   ├── redir/           # Redirection handling
│   ├── signals/         # Signal handling
│   └── utils/           # Utility functions
├── main.c               # Main program entry
└── Makefile             # Build configuration
```
## Architecture
BalkanShell follows a classic shell architecture with these main components:
1. **Lexer**: Tokenizes the input string into meaningful tokens (commands, arguments, operators)
2. **Parser**: Analyzes the tokens and builds a command structure
3. **Executor**: Executes the parsed commands, handling redirections and pipes
4. **Built-ins**: Implements shell built-in commands
5. **Environment Manager**: Manages environment variables
### Data Flow
1. User inputs a command
2. The lexer breaks it into tokens
3. The parser creates a command structure
4. The executor runs the command with appropriate redirections
5. Output is displayed to the user
6. The shell returns to the prompt for the next command
## Development
### Building from Source
```bash
# Standard build
make
# Clean object files
make clean
# Full clean (objects and executable)
make fclean
# Rebuild
make re
```
## Contributing
Contributions are welcome! If you'd like to contribute to BalkanShell:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
Please make sure your code follows the project's coding style and includes appropriate tests.
## License
This project is licensed under the MIT License - see the LICENSE file for details.
## Acknowledgments
- 42 School for the project requirements and educational framework
- The GNU Bash project for inspiration
- Contributors to the Readline library
---
*Note: This project was developed as part of the 42 School curriculum and is intended for educational purposes.*
