# Linux for Developers 👩‍💻

## Setting Up Development Environment

Setting up a development environment in Linux involves configuring tools and dependencies required for software development. Linux distributions offer various package managers to simplify the installation of development tools.

### 1. Installing Essential Development Tools

#### Using apt Package Manager (Ubuntu/Debian):

1. **Update package index:**
   ```bash
   sudo apt update
   ```

2. **Install essential development tools:**
   ```bash
   sudo apt install build-essential
   ```

   - `build-essential` includes compilers (gcc), make, and other essential build tools.

### 2. Choosing a Text Editor or Integrated Development Environment (IDE)

#### Text Editors:
- **Nano**: Simple and beginner-friendly text editor.
  ```bash
  sudo apt install nano
  ```

- **Vim**: Powerful and highly configurable text editor.
  ```bash
  sudo apt install vim
  ```

#### IDEs:
- **Visual Studio Code**: Lightweight and extensible IDE with a rich ecosystem of extensions.
  - Download from [Visual Studio Code website](https://code.visualstudio.com/) or install via package manager.

- **Eclipse**: Comprehensive IDE for Java, C/C++, and other languages.
  ```bash
  sudo apt install eclipse
  ```

## Version Control with Git

Git is a distributed version control system widely used in software development to track changes, collaborate on projects, and manage codebases efficiently.

### Installing Git

#### Using apt Package Manager:

1. **Install Git:**
   ```bash
   sudo apt install git
   ```

2. **Verify installation:**
   ```bash
   git --version
   ```

### Setting Up Git

#### Configure Git Global Settings:

1. **Set username:**
   ```bash
   git config --global user.name "Your Name"
   ```

2. **Set email:**
   ```bash
   git config --global user.email "your.email@example.com"
   ```

### Basic Git Workflow

#### Cloning a Repository:

```bash
git clone https://github.com/example/repository.git
cd repository
```

#### Creating a New Repository:

```bash
mkdir new_project
cd new_project
git init
```

#### Git Commands

- **git add**: Add changes to the staging area.
  ```bash
  git add file.txt
  ```

- **git commit**: Commit changes with a descriptive message.
  ```bash
  git commit -m "Add new feature"
  ```

- **git push**: Push changes to a remote repository.
  ```bash
  git push origin main
  ```

- **git pull**: Pull latest changes from a remote repository.
  ```bash
  git pull origin main
  ```

## Common Development Tools

### 1. gcc (GNU Compiler Collection)

**gcc** is a powerful compiler for C, C++, and other programming languages. It translates source code into executable programs.

#### Installing gcc

```bash
sudo apt install gcc
```

#### Compiling a C Program

1. **Create a C source file (`hello.c`):**
   ```c
   #include <stdio.h>

   int main() {
       printf("Hello, World!\n");
       return 0;
   }
   ```

2. **Compile using gcc:**
   ```bash
   gcc -o hello hello.c
   ```

3. **Run the compiled program:**
   ```bash
   ./hello
   ```

### 2. make

**make** is a build automation tool that manages dependencies and executes commands to build software projects from source code.

#### Example Makefile (`Makefile`)

```make
CC=gcc
CFLAGS=-I.

app: main.o functions.o
    $(CC) -o app main.o functions.o

main.o: main.c
    $(CC) -c -o main.o main.c $(CFLAGS)

functions.o: functions.c
    $(CC) -c -o functions.o functions.c $(CFLAGS)

clean:
    rm -f *.o app
```

#### Commands:

- **make**: Build the target specified in the Makefile.
  ```bash
  make
  ```

- **make clean**: Remove object files and executable.
  ```bash
  make clean
  ```

### 3. Integrated Development Environments (IDEs)

#### Visual Studio Code

- **Extensions**: Install extensions for language support, debugging, and version control.

#### Eclipse

- **Project Setup**: Create and manage projects with built-in tools for debugging and profiling.

## Summary

Linux provides a robust environment for software development with powerful tools like gcc, make, and versatile text editors or IDEs. Git facilitates version control and collaboration, enabling developers to track changes and manage code efficiently. Setting up a development environment on Linux involves installing essential tools, configuring version control, and choosing suitable editors or IDEs based on project requirements. Understanding these fundamentals empowers developers to write, build, and manage software effectively in a Linux environment.

