# Microshell

A minimal Unix shell implementation in C, created as part of the 42 and 1337 coding school projects.

## 📋 Description

Microshell is a simplified shell program that implements basic command execution, piping, and built-in commands. This project is part of the **42 Network** curriculum and specifically from **1337** (42's campus in Morocco), designed to deepen understanding of process management, file descriptors, and system calls in Unix-like operating systems.

## 🎯 Project Context

This project is part of:
- **42 Network**: A global education initiative in computer programming
- **1337**: 42's coding school in Morocco (Khouribga and Ben Guerir)
- **42 Exam Practice**: Preparing students for evaluation on system programming concepts

## ✨ Features

The microshell implements the following functionality:

- **Command Execution**: Execute system commands using `execve`
- **Pipe Support**: Chain commands using the pipe operator `|`
- **Command Separator**: Run multiple commands sequentially using `;`
- **Built-in `cd`**: Change directory with proper error handling
- **Error Handling**: Comprehensive error messages for various failure scenarios

## 🔧 Compilation

Compile the program using gcc:

```bash
gcc -Wall -Wextra -Werror microshell.c -o microshell
```

## 🚀 Usage

Run the microshell with commands as arguments:

```bash
./microshell /bin/ls "|" /usr/bin/grep microshell ";" /bin/echo done
```

### Examples

1. **Simple command execution:**
   ```bash
   ./microshell /bin/ls -la
   ```

2. **Using pipes:**
   ```bash
   ./microshell /bin/ls "|" /usr/bin/grep .c
   ```

3. **Multiple commands with semicolon:**
   ```bash
   ./microshell /bin/ls ";" /bin/pwd ";" /bin/echo "Hello 42"
   ```

4. **Change directory:**
   ```bash
   ./microshell cd /tmp ";" /bin/pwd
   ```

## 📚 Implementation Details

### Key Components

- **`exec()`**: Main execution function handling pipes and command execution
- **`cd()`**: Built-in command for directory changes
- **`set_pipe()`**: Helper function for pipe setup and file descriptor management
- **`err()`**: Error output utility function

### Technical Highlights

- Process creation using `fork()`
- Inter-process communication via `pipe()`
- File descriptor manipulation with `dup2()`
- Process synchronization using `waitpid()`
- Command execution through `execve()`

## ⚠️ Error Handling

The microshell provides clear error messages for:
- `error: cd: bad arguments` - Incorrect number of arguments for cd
- `error: cd: cannot change directory to [path]` - Failed directory change
- `error: cannot execute [command]` - Command execution failure
- `error: fatal` - Critical system call failures

## 🎓 Learning Objectives

This project helps students understand:
- Process management in Unix systems
- File descriptors and I/O redirection
- Inter-process communication
- System call interfaces
- Memory and resource management

## 📖 42 and 1337

**42** is a revolutionary coding school with a peer-to-peer learning methodology. **1337** is the Moroccan branch of 42, offering free, high-quality education in programming.

Learn more:
- [42 Network](https://www.42.fr/)
- [1337 Coding School](https://1337.ma/)

## 📄 License

This is an educational project for 42/1337 students.

---

*Made with ❤️ as part of the 42 Network curriculum at 1337*
