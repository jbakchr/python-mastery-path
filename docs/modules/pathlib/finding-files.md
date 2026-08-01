# pathlib - Writing Files

## Overview

Finding files is one of the most common filesystem tasks.

Developers frequently need to locate files before they can read, analyze, organize, copy, or process them.

Examples include:

- Finding all Markdown files in a notes directory
- Locating Python files in a project
- Gathering log files for analysis
- Searching for configuration files
- Building automation tools that work across many files

The pathlib module provides powerful ways to search directories using patterns and recursive searches.

Mastering file discovery is an important step toward practical filesystem automation.

---

## Learning Progression

The exercises in this capability are organized into four stages:

```
Discover
    ↓
Apply
    ↓
Compose
    ↓
Automate
```

Each stage builds on the previous one, gradually moving from understanding a capability to using it in practical automation tasks.

---

## **Discover**

### PATHLIB-FF-01

#### Scenario

You have a directory containing several documents.

Before you can read or process those files, you first need a way to discover which files exist inside the directory.

A common first step is listing all files in a folder.

#### Objective

Create a Path object representing a directory named:

```
documents
```

Print every item contained directly inside that directory.

#### Success Criteria

Your program should:

- Create a Path object for documents
- List all items inside the directory
- Print each item

#### Need a Hint?

??? tip "Small Hint"

    Path objects provide a method for iterating over the contents of a directory.

??? tip "Stronger Hint"

    Look for a method that returns each item immediately contained within a directory.

??? tip "Almost There"

    Use:
    ```python
    path.iterdir()
    ```

    and loop through the results.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    documents = Path("documents")

    for item in documents.iterdir():
        print(item)
    ```

#### Why This Exercise Exists

Finding files starts with understanding how to explore a directory.

Many real-world tasks begin by discovering what files are available before deciding which ones to process.

Examples include:

- File organizers
- Backup tools
- Report generators
- Code analysis tools

This exercise introduces the fundamental capability of listing directory contents.

---

### PATHLIB-FF-02

#### Scenario

You are working in a directory containing many different file types:

```
notes.txt
todo.txt
report.pdf
image.png
```

You only want to work with text files.

Instead of processing every file, you'd like Python to find only files matching a specific pattern.

#### Objective

Create a Path object for a directory named:

```
documents
```

Find and print all .txt files in the directory.

#### Success Criteria

Your program should:

- Create a Path object
- Search for files ending in .txt
- Print each matching file

#### Need a Hint?

??? tip "Small Hint"

    pathlib supports wildcard patterns when searching for files.

??? tip "Stronger Hint"

    The wildcard `*` can represent any filename.

??? tip "Almost There"

    Use:

    ```python
    path.glob("*.txt")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    documents = Path("documents")

    for file in documents.glob("*.txt"):
        print(file)
    ```

#### Why This Exercise Exists

Most programs don't work with every file in a directory.

They typically target files of a specific type.

Examples include:

- Finding Markdown documentation
- Locating Python source files
- Processing CSV exports
- Searching log files

Pattern-based searches make it possible to locate only the files you care about.

---

### PATHLIB-FF-03

#### Scenario

Your notes are organized into many nested folders:

```
notes/
├── work/
├── personal/
├── learning/
└── archive/
```

You want to find every Markdown file regardless of which folder it lives in.

Searching a single directory is no longer enough.

You need to search an entire directory tree.

#### Objective

Create a Path object representing:

```
notes
```

Find and print every Markdown file (.md) within the directory and all of its subdirectories.

#### Success Criteria

Your program should:

- Create a Path object
- Search recursively through subdirectories
- Find all .md files
- Print each result

#### Need a Hint?

??? tip "Small Hint"

    pathlib provides a recursive version of `glob()`.

??? tip "Stronger Hint"

    Recursive searches look inside subdirectories as well as the current directory.

??? tip "Almost There"

    Use:

    ```python
    path.rglob("*.md")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    for file in notes.rglob("*.md"):
        print(file)
    ```

#### Why This Exercise Exists

Many real-world projects store files across multiple folders.

Examples include:

- Source code repositories
- Documentation sites
- Note-taking systems
- Log archives

Recursive searching is one of the most powerful capabilities in pathlib because it allows programs to discover files throughout an entire directory structure.

---

## **Apply**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

## PATHLIB-FF-04

### Scenario

You are troubleshooting an application that stores log files in multiple folders.

You need to locate every log file before you can investigate what happened.

Example files:

```text
logs/
├── app.log
├── database.log
├── archive/
│   └── old.log
└── errors/
    └── latest.log
```

### Objective

Create a `Path` object representing:

```text
logs
```

Find every `.log` file within the directory and all of its subdirectories.

Print each matching file.

### Success Criteria

Your program should:

- Create a Path object for `logs`
- Search recursively through all subdirectories
- Find every `.log` file
- Print each matching path

### Need a Hint?

??? tip "Small Hint"

    The log files may exist in nested directories.

??? tip "Stronger Hint"

    A recursive search will look inside the directory and all subdirectories.

??? tip "Almost There"

    Use:

    ```python
    path.rglob("*.log")
    ```

### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    logs = Path("logs")

    for file in logs.rglob("*.log"):
        print(file)
    ```

### Why This Exercise Exists

Log files are commonly distributed across several directories.

Many debugging, monitoring, and reporting tools begin by locating all relevant log files before analyzing their contents.

This exercise reinforces recursive file discovery in a realistic troubleshooting scenario.

---

## PATHLIB-FF-05

### Scenario

You are exploring a Python project and want to understand its structure.

Before reading the code, you would like to see every Python source file in the repository.

### Objective

Create a `Path` object representing:

```text
project
```

Find all Python files (`.py`) located anywhere within the project directory.

Print each file that is found.

### Success Criteria

Your program should:

- Create a Path object
- Search all subdirectories
- Find every `.py` file
- Print each matching file

### Need a Hint?

??? tip "Small Hint"

    Python files use a specific file extension.

??? tip "Stronger Hint"

    Use a recursive search pattern that matches Python files.

??? tip "Almost There"

    Use:

    ```python
    path.rglob("*.py")
    ```

### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    for file in project.rglob("*.py"):
        print(file)
    ```

### Why This Exercise Exists

Source code often spans many directories.

Tools such as documentation generators, linters, code analyzers, and testing utilities frequently begin by locating Python files across an entire project.

This exercise demonstrates how file discovery supports software development workflows.

---

### PATHLIB-FF-06

#### Scenario

You maintain a collection of notes written in Markdown.

The notes are organized into categories such as:

```text
notes/
├── work/
├── personal/
├── learning/
└── archive/
```

You would like to generate a list of every Markdown document you have written.

#### Objective

Create a `Path` object representing:

```text
notes
```

Find all Markdown files (`.md`) contained within the directory and its subdirectories.

Print each matching file.

#### Success Criteria

Your program should:

- Create a Path object
- Search recursively
- Find every `.md` file
- Print each matching path

#### Need a Hint?

??? tip "Small Hint"

    Markdown files share the same file extension.

??? tip "Stronger Hint"

    Use a search pattern that matches all Markdown files.

??? tip "Almost There"

    Use:

    ```python
    path.rglob("*.md")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    for file in notes.rglob("*.md"):
        print(file)
    ```

#### Why This Exercise Exists

Documentation systems, knowledge bases, and note-taking tools often need to discover Markdown files before they can process them.

This exercise reinforces the idea that file discovery is frequently the first step in larger automation tasks.
``

---

## **Compose**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

### PATHLIB-FF-07

#### Scenario

You are reviewing a project before sharing it with a teammate.

You want a quick overview of the different types of files contained in the repository.

Specifically, you would like to identify:

- Python files
- Markdown files
- JSON files

#### Objective

Create a `Path` object representing:

```text
project
```

Find all:

- `.py` files
- `.md` files
- `.json` files

Print the files grouped by type.

#### Success Criteria

Your program should:

- Create a Path object
- Search recursively through the project
- Locate Python, Markdown, and JSON files
- Print the results grouped by file type

#### Need a Hint?

??? tip "Small Hint"

    You can perform more than one search on the same directory.

??? tip "Stronger Hint"

    Consider using `rglob()` with a different pattern for each file type.

??? tip "Almost There"

    Search separately for:

    ```python
    "*.py"
    "*.md"
    "*.json"
    ```

#### Solution

???\*success "Show Solution"

    ```py*hon
    from pathlib import Path

- project = Path("project")

  *rint("Python files:")
  for file*in project.rglob("*.py"):
  *rint(file)

  print("\nMarkdown *iles:")
  for file in project.rg*ob("\*.md"):
  print(file)

- print("\nJSON files:")
  for f*le in project.rglob("*.json"):
- print(file)


    ```

#### Why T\*is Exercise Exists

Real projects *ften contain many different file t*pes.

Before building automation, *evelopers frequently need to under*tand what files exist and how they\*are organized.

This exercise comb*nes multiple file searches to buil* a broader picture of a directory \*tructure.

---

### PATHLIB-FF-08

#### Scenario

You are organizing a \*arge notes collection.

Your notes*are stored as Markdown files insid* many different folders.

You woul\* like to see both:

- the file nam\*
- the folder containing the file
  _for every note that is discovered._

#### Objective

Create a `Path` ob\*ect representing:

```text
notes
```

Find all Markdown files within *he directory tree.

For each file,*print:

- the file name
- its pare*t directory

#### Success Criteria
*Your program should:

- Search rec*rsively for Markdown files
- Acces* information about each file
- Pri*t the file name
- Print the parent*directory

#### Need a Hint?

??? tip "Small Hint"

    A found file i* still a `Path` object.

??? tip "Stronger Hint"

    Path objects ex*ose useful attributes that describ* the file and its location.

??? tip "Almost There"

    Look at:

    ```python
    file.name
    file.*arent
    ```

### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    for file in notes.rglob("*.md"):
        print(f"File: {file.name}")
        print(f"Folder: {file.parent}")
        print()
    ```

#### Why This*Exercise Exists

Finding files is *sually only the first step.

Once a file has been discovered, developors often need information about the file itself.

This exercise combines file discovery with path inspection, reinforcing earlier capabilit*es from the module.

---

### PATHLIB-FF-09

#### Scenario

You are responsible for maintaining a documentation site.

Before publishing the site, you want to know how many Markdown documents currently exist.

The files may be scattered throughout many subdirectories.

#### Objective

Create a `Path` object representing:

```text
docs
```

Find all Markdown files and display the total number found.

#### Success Criteria

Your program should:

- Search recursively for Markdown files
- Count how many files were found
- Print the total count

#### Need a Hint?

??? tip "Small Hint"

    A recursive search produces multiple Path objects.

??? tip "Stronger Hint"

    You may need to convert the results into a collection before counting them.

??? tip "Almost There"

    Consider:

    ```python
    files = list(path.rglob("*.md"))
    ```

    Then use:

    ```python
    len(files)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    docs = Path("docs")

    files = list(docs.rglob("*.md"))

    print(f"Total Markdown files: {len(files)}")
    ```

#### Why This Exercise Exists

Many automation tasks involve gathering information rather than simply listing files.

Examples include:

- Counting documentation pages
- Measuring project size
- Generating reports
- Tracking content growth

This exercise combines file discovery with basic reporting and prepares learners for the larger automation exercises that follow.

---

## **Automate**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

### PATHLIB-FF-10

#### Scenario

You maintain a personal knowledge base containing hundreds of notes spread across many folders.

Before making changes to the collection, you want a quick report showing all Markdown files currently stored in the knowledge base.

Instead of manually searching through folders, you decide to automate the process.

#### Objective

Create a program that:

- Searches a directory named `notes`
- Finds all Markdown files (`.md`)
- Prints each file that was found
- Displays the total number of Markdown files

#### Success Criteria

Your program should:

- Create a Path object
- Search recursively for Markdown files
- Print each matching file
- Display the total file count

#### Need a Hint?

??? tip "Small Hint"

    You need both the list of files and the number of files found.

??? tip "Stronger Hint"

    Consider storing the search results before printing them.

??? tip "Almost There"

    Use:

    ```python
    files = list(notes.rglob("*.md"))
    ```

    Then print the files and use `len(files)`.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    files = list(notes.rglob("*.md"))

    for file in files:
        print(file)

    print(f"\nTotal Markdown files: {len(files)}")
    ```

#### Why This Exercise Exists

Automation often begins with generating useful reports.

Before files can be analyzed, organized, copied, or modified, they first need to be discovered.

This exercise combines recursive searching and reporting into a simple but practical automation task.

---

### PATHLIB-FF-11

#### Scenario

You are cleaning up a project repository and want to identify large files that may not belong in source control.

Manually inspecting every file would be slow and error-prone.

You decide to automate the process.

#### Objective

Create a program that:

- Searches a directory named `project`
- Finds all files recursively
- Prints files larger than 1 MB

#### Success Criteria

Your program should:

- Search the entire directory tree
- Inspect each discovered file
- Check the file size
- Print files larger than 1 MB

#### Need a Hint?

??? tip "Small Hint"

    After finding a file, pathlib can provide information about it.

??? tip "Stronger Hint"

    There is a method that returns file metadata, including its size.

??? tip "Almost There"

    Use:

    ```python
    file.stat().st_size
    ```

    to retrieve the file size in bytes.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    for file in project.rglob("*"):
        if file.is_file():
            if file.stat().st_size > 1_000_000:
                print(file)
    ```

#### Why This Exercise Exists

Many practical automation tasks involve finding files and then filtering them based on additional criteria.

Examples include:

- Identifying large files
- Finding old files
- Locating files that should be archived
- Checking repository health

This exercise combines file discovery with file inspection to solve a realistic maintenance problem.

---

### PATHLIB-FF-12

#### Scenario

You are creating a simple repository scanner.

Before exploring a codebase, you would like a quick summary of the types of files it contains.

Specifically, you want to know how many:

- Python files
- Markdown files
- JSON files

exist within the repository.

#### Objective

Create a program that:

- Searches a directory named `repository`
- Counts all `.py` files
- Counts all `.md` files
- Counts all `.json` files
- Prints a summary report

#### Success Criteria

Your program should:

- Search recursively
- Count multiple file types
- Print a readable report

Example output:

```text
Python files: 15
Markdown files: 8
JSON files: 3
```

#### Need a Hint?

??? tip "Small Hint"

    Each file type can be searched independently.

??? tip "Stronger Hint"

    Use a separate recursive search for each extension.

??? tip "Almost There"

    Store the results in lists and use:

    ```python
    len(...)
    ```

    to calculate the counts.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    repository = Path("repository")

    python_files = list(repository.rglob("*.py"))
    markdown_files = list(repository.rglob("*.md"))
    json_files = list(repository.rglob("*.json"))

    print(f"Python files: {len(python_files)}")
    print(f"Markdown files: {len(markdown_files)}")
    print(f"JSON files: {len(json_files)}")
    ```

#### Why This Exercise Exists

Many developer tools begin by scanning a directory and building an inventory of files.

Examples include:

- Documentation generators
- Static analysis tools
- Repository dashboards
- Build systems

This exercise feels like the first step toward a real tool rather than a standalone exercise.

It combines recursive searching, filtering, counting, and reporting into a practical filesystem automation task.