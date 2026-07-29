# pathlib - Reading Files

## **Overview**

---

## **Learning Progression**

The exercises in this section are organized into four stages:

```text
Discover
    ↓
Apply
    ↓
Compose
    ↓
Automate
```

---

## **Discover**

_**Goal:**_

👉 Learn the capability.

---

### PATHLIB-RF-01

#### Scenario

You keep a todo list in a file:

```
notes/todo.txt
```

You want to see everything written in the file.

#### Objective

Create a Path object representing:

```
notes/todo.txt
```

Read the contents of the file and print them.

#### Success Criteria

Your program should:

- Create a Path object
- Read the file contents
- Print the contents to the console

#### Need a Hint?

??? tip "Small Hint"

    pathlib can read the contents of a text file directly.

??? tip "Stronger Hint"

    Look for a method that returns all text from a file.

??? tip "Almost There"

    Use:

    ```python
    path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/todo.txt")

    print(path.read_text())
    ```

#### Why This Exercise Exists

Reading file contents is one of the most common filesystem tasks.

Many programs begin by opening a file so they can inspect, process, or analyze its contents.

---

### PATHLIB-RF-02

#### Scenario

You have written some notes for a project in:

```
notes/project-ideas.txt
```

Before continuing your work, you want to display the contents of the file.

#### Objective

Create a Path object representing:

```
notes/project-ideas.txt
```

Read and print the contents.

#### Success Criteria

Your program should:

- Create a Path object
- Read the file contents
- Print the contents

#### Need a Hint?

??? tip "Small Hint"

    Once you have a Path object, you can use it to access the file's text.

??? tip "Stronger Hint"

    The method returns the entire contents as a string.

??? tip "Almost There"

    Use:

    ```python
    path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/project-ideas.txt")

    contents = path.read_text()

    print(contents)
    ```

#### Why This Exercise Exists

Many applications store information in text files.

Being able to read a file is the first step toward processing that information with Python.

---

### PATHLIB-RF-03

#### Scenario

You join a new software project.

The repository contains a file named:

```
README.md
```

You want to read the documentation stored inside the file.

#### Objective

Create a Path object representing:

```
README.md
```

Read and display its contents.

#### Success Criteria

Your program should:

- Create a Path object
- Read the file contents
- Print the contents

#### Need a Hint?

??? tip "Small Hint"

    README files are plain text files.

??? tip "Stronger Hint"

    Path objects can read text directly without using open().

??? tip "Almost There"

    Use:

    ```python
    path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("README.md")

    print(path.read_text())
    ```

#### Why This Exercise Exists

Reading documentation files is a common developer task.

This exercise demonstrates how pathlib can be used to quickly access file contents.

---

### PATHLIB-RF-04

#### Scenario

Your application stores its configuration in:

```
config.txt
```

You need to load the configuration so it can be displayed to the user.

#### Objective

Create a Path object representing:

```
config.txt
```

Read the file contents and store them in a variable named `config`.

Print the contents.

#### Success Criteria

Your program should:

- Create a Path object
- Read the file contents
- Store the contents in a variable named `config`
- Print the contents

#### Need a Hint?

??? tip "Small Hint"

    The contents returned by pathlib are text.

??? tip "Stronger Hint"

    Save the result of reading the file into a variable.

??? tip "Almost There"

    Use:

    ```python
    config = path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("config.txt")

    config = path.read_text()

    print(config)
    ```

#### Why This Exercise Exists

Applications often read information from configuration files before doing any other work.

This exercise introduces the idea that file contents can be stored and used later in a program.

---

### PATHLIB-RF-05

#### Scenario

You are building a journal application.

Journal entries are stored in text files.

Today's entry is located at:

```
journal/today.txt
```

You want to load the entry so it can be displayed inside the application.

#### Objective

Create a Path object representing:

```
journal/today.txt
```

Read the contents of the file and store them in a variable named `entry`.

Print the contents.

#### Success Criteria

Your program should:

- Create a Path object
- Read the file contents
- Store the contents in a variable named `entry`
- Print the contents

#### Need a Hint?

??? tip "Small Hint"

    Read the contents before printing them.

??? tip "Stronger Hint"

    The text returned by pathlib can be stored in a variable.

??? tip "Almost There"

    Use:

    ```python
    entry = path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("journal/today.txt")

    entry = path.read_text()

    print(entry)
    ```

#### Why This Exercise Exists

Many applications load text from files before displaying or processing it.

This exercise reinforces the core capability of reading file contents and storing them for later use.

---

## **Apply**

_Goal:_

👉 Use the capability.

---

### PATHLIB-RF-06

#### Scenario

You keep a daily journal in text files.

Today's entry is stored in:

```
journal/today.txt
```

Before adding a new entry, you want to see what was already written.

#### Objective

Read the contents of the file and display them with a heading.

#### Success Criteria

Your program should:

- Create a Path object
- Read the file contents
- Print:

```text
Journal Entry:
```

followed by the file contents.

#### Need a Hint?

??? tip "Small Hint"

    Read the file first, then display it.

??? tip "Stronger Hint"

    Store the contents in a variable before printing.

??? tip "Almost There"

    Use:

    ```python
    entry = path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("journal/today.txt")

    entry = path.read_text()

    print("Journal Entry:")
    print(entry)
    ```

#### Why This Exercise Exists

Many applications display file contents as part of a user interface.

Reading a file is often immediately followed by presenting the contents to a user.

---

### PATHLIB-RF-07

#### Scenario

You are reviewing a project README file.

You want to know how much documentation is available without reading the entire file.

#### Objective

Read the contents of:

```
README.md
```

Count the number of characters in the file.

Print the result.

#### Success Criteria

Your program should:

- Read the file contents
- Count the characters
- Print the total number

#### Need a Hint?

??? tip "Small Hint"

    The contents returned by `read_text()` are a string.

??? tip "Stronger Hint"

    Python can determine the length of a string.

??? tip "Almost There"

    Use:

    ```python
    len(contents)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("README.md")

    contents = path.read_text()

    print(len(contents))
    ```

#### Why This Exercise Exists

Reading a file is often the first step.

Analyzing the contents is usually the second step.

This exercise introduces the idea that file contents can be processed like any other Python string.

---

### PATHLIB-RF-08

#### Scenario

You maintain a shopping list stored in:

```
shopping-list.txt
```

You want to know how many items have been written in the file.

Each item appears on its own line.

#### Objective

Read the file and count the number of lines.

Print the total.

#### Success Criteria

Your program should:

- Read the file contents
- Split the contents into lines
- Print the number of lines

#### Need a Hint?

??? tip "Small Hint"

    The file contents are returned as a single string.

??? tip "Stronger Hint"

    Strings can be split into lines.

??? tip "Almost There"

    Use:

    ```python
    contents.splitlines()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("shopping-list.txt")

    contents = path.read_text()

    lines = contents.splitlines()

    print(len(lines))
    ```

#### Why This Exercise Exists

Many real-world files store records one line at a time.

Examples include:

- Shopping lists
- Todo lists
- Log files
- Configuration files

Being able to work with lines is an important practical skill.

---

### PATHLIB-RF-09

#### Scenario

You manage a notes file containing meeting information.

You want to check whether the word:

```
Python
```

appears anywhere in the file.

#### Objective

Read the file contents and determine whether the word:

Python

exists in the text.

#### Success Criteria

Your program should print:

```text
Found
```

or

```text
Not Found
```

#### Need a Hint?

??? tip "Small Hint"

    After reading a file, you have a string.

??? tip "Stronger Hint"

    Python strings can be searched for text.

??? tip "Almost There"

    Use:

    ```python
    "Python" in contents
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("meeting-notes.txt")

    contents = path.read_text()

    if "Python" in contents:
        print("Found")
    else:
        print("Not Found")
    ```

#### Why This Exercise Exists

Many applications search file contents for keywords.

Examples include:

- Search tools
- Documentation systems
- Log analyzers
- Content management systems

Reading files often provides the data that later needs to be searched.

---

### PATHLIB-RF-10

#### Scenario

Your application stores user information inside:

```
users.txt
```

Before processing the file, you want a quick overview of its contents.

#### Objective

Read the file and display:

- Number of characters
- Number of lines

#### Success Criteria

Your program should produce output similar to:

```text
Characters: 250
Lines: 12
```

#### Need a Hint?

??? tip "Small Hint"

    Read the file once and reuse the contents.

??? tip "Stronger Hint"

    You will need to calculate two different values.

??? tip "Almost There"

    Use:

    ```python
    len(contents)
    ```

    and

    ```python
    len(contents.splitlines())
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("users.txt")

    contents = path.read_text()

    print(f"Characters: {len(contents)}")
    print(f"Lines: {len(contents.splitlines())}")
    ```

#### Why This Exercise Exists

Developers frequently inspect file contents before deciding how to process them.

Simple metrics such as character counts and line counts provide useful information about a file and often act as the first step in larger automation tasks.

---

## **Compose**

_Goal:_

👉 Combine capabilities.

---

### PATHLIB-RF-11

#### Scenario

You are exploring a new software project.

You discover the file:

```
README.md
```

You want to learn:

- What the file is called
- What type of file it is
- What the file contains

#### Objective

Create a Path object and display:

- Filename
- Extension
- File contents

#### Success Criteria

Your program should:

- Create a Path object
- Display the filename
- Display the extension
- Display the file contents

#### Need a Hint?

??? tip "Small Hint"

    First inspect the path, then read the file.

??? tip "Stronger Hint"

    Combine the inspection capabilities with `read_text()`.

??? tip "Almost There"

    Use:

    ```python
    - path.name
    - path.suffix
    - path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("README.md")

    print(f"Filename: {path.name}")
    print(f"Extension: {path.suffix}")
    print()

    print(path.read_text())
    ```

#### Why This Exercise Exists

Real-world tools often need information about a file before processing it.

This exercise combines path inspection and file reading into a single workflow.

---

### PATHLIB-RF-12

#### Scenario

You are reviewing a configuration file.

Before using it, you want to verify that it exists and then display its contents.

The file is:

```
config.txt
```

#### Objective

Create a Path object.

If the file exists:

- Print "Configuration Loaded"
- Display the contents

Otherwise print:

```text
Configuration Not Found
```

#### Success Criteria

Your program should:

- Check whether the file exists
- Read the file if it exists
- Display an appropriate message

#### Need a Hint?

??? tip "Small Hint"

    Don't attempt to read the file until you know it exists.

??? tip "Stronger Hint"

    Combine existence checking with file reading.

??? tip "Almost There"

    Use:

    ```python
    path.exists()
    ```

    before:

    ```python
    path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("config.txt")

    if path.exists():
        print("Configuration Loaded")
        print(path.read_text())
    else:
        print("Configuration Not Found")
    ```

#### Why This Exercise Exists

Many programs need to inspect a file before reading it.

This helps prevent errors when files are missing.

---

### PATHLIB-RF-13

#### Scenario

You maintain a collection of notes.

One file contains meeting notes:

```
notes/meeting-notes.txt
```

You want a quick summary showing:

- Filename
- Number of characters
- Number of lines

#### Objective

Generate a summary for the file.

#### Success Criteria

Your program should produce output similar to:

```text
Filename: meeting-notes.txt
Characters: 142
Lines: 8
```

#### Need a Hint?

??? tip "Small Hint"

    Read the file contents once and reuse them.

??? tip "Stronger Hint"

    You'll need both path information and file contents.

??? tip "Almost There"

    Combine:

    - path.name
    - len(contents)
    - len(contents.splitlines())

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/meeting-notes.txt")

    contents = path.read_text()

    print(f"Filename: {path.name}")
    print(f"Characters: {len(contents)}")
    print(f"Lines: {len(contents.splitlines())}")
    ```

#### Why This Exercise Exists

Many tools create summaries of files before performing more advanced analysis.

This exercise combines inspection and content analysis.

---

### PATHLIB-RF-14

#### Scenario

You are reviewing documentation for a project.

The documentation is stored in:

```
docs/getting-started.md
```

You want to know whether the document mentions Python.

#### Objective

Read the contents of the file and determine whether the word:

```
Python
```

appears in the document.

Display:

```text
Mentioned
```

or

```text
Not Mentioned
```

#### Success Criteria

Your program should:

- Read the file contents
- Search for the word "Python"
- Display the result

#### Need a Hint?

??? tip "Small Hint"

    After reading a file, you have a string.

??? tip "Stronger Hint"

    Strings can be searched using the `in` operator.

??? tip "Almost There"

    Use:

    ```python
    "Python" in contents
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("docs/getting-started.md")

    contents = path.read_text()

    if "Python" in contents:
        print("Mentioned")
    else:
        print("Not Mentioned")
    ```

#### Why This Exercise Exists

Many applications search documents for keywords, phrases, or identifiers.

This exercise combines file reading with basic content analysis.

---

### PATHLIB-RF-15

#### Scenario

You are building a simple document inspector.

Given a file, the tool should generate a useful report describing both the file and its contents.

The file is:

notes/project-plan.txt

#### Objective

Display:

- Filename
- Extension
- Character Count
- Line Count

#### Success Criteria

Your program should produce output similar to:

```text
Filename: project-plan.txt
Extension: .txt
Characters: 340
Lines: 15
```

#### Need a Hint?

??? tip "Small Hint"

    This exercise combines everything you've learned so far.

??? tip "Stronger Hint"

    Inspect the file and then analyze its contents.

??? tip "Almost There"

    Use:

    ```python
    - path.name
    - path.suffix
    - path.read_text()
    - len()
    - splitlines()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/project-plan.txt")

    contents = path.read_text()

    print(f"Filename: {path.name}")
    print(f"Extension: {path.suffix}")
    print(f"Characters: {len(contents)}")
    print(f"Lines: {len(contents.splitlines())}")
    ```

#### Why This Exercise Exists

Many real-world tools gather information about files before deciding what action to take.

This exercise acts as a capstone for Reading Files by combining:

- Path creation
- Path inspection
- File reading
- Content analysis

into a single practical workflow.

---

## **Automate**

_Goal:_

👉 Automate solutions.

---

### PATHLIB-RF-16

#### Scenario

You keep notes about different projects in separate files.

You want to quickly review all of them without opening each file manually.

The files are:

```
- notes/project-a.txt
- notes/project-b.txt
- notes/project-c.txt
```

#### Objective

Read each file and display its contents.

#### Success Criteria

Your program should:

- Create Path objects for each file
- Read each file
- Print the contents of each file

#### Need a Hint?

??? tip "Small Hint"

    Store the paths in a collection.

??? tip "Stronger Hint"

    Use a loop to process one file at a time.

??? tip "Almost There"

    For each path:

    ```python
    path.read_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("notes/project-a.txt"),
        Path("notes/project-b.txt"),
        Path("notes/project-c.txt"),
    ]

    for path in paths:
        print(path.read_text())
        print()
    ```

#### Why This Exercise Exists

Automation often involves processing groups of files rather than individual files.

This exercise demonstrates how reading files can be combined with loops to handle repetitive tasks efficiently.

---

### PATHLIB-RF-17

#### Scenario

You are reviewing documentation for a project.

Several README files exist:

```
- README.md
- docs/setup.md
- docs/deployment.md
```

You want to know how much content each file contains.

#### Objective

Read each file and display:

- Filename
- Character Count

#### Success Criteria

Your program should produce output similar to:

```text
README.md: 542 characters
setup.md: 238 characters
deployment.md: 714 characters
```

#### Need a Hint?

??? tip "Small Hint"

    Read each file once and reuse the contents.

??? tip "Stronger Hint"

    Character count can be calculated using `len()`.

??? tip "Almost There"

    Combine:

    ```python
    path.name
    ```

    and

    ```python
    len(contents)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("README.md"),
        Path("docs/setup.md"),
        Path("docs/deployment.md"),
    ]

    for path in paths:
        contents = path.read_text()
        print(f"{path.name}: {len(contents)} characters")
    ```

#### Why This Exercise Exists

Many automation tools analyze files and generate summaries.

File statistics often provide useful insights before more advanced processing takes place.

---

### PATHLIB-RF-18

#### Scenario

You have several todo lists stored in different files.

You want to know how many tasks are recorded in total.

The files are:

- personal-todos.txt
- work-todos.txt
- project-todos.txt

Each task appears on its own line.

#### Objective

Read all files and calculate the total number of lines across all files.

#### Success Criteria

Your program should:

- Read every file
- Count the lines in each file
- Print the total number of tasks

#### Need a Hint?

??? tip "Small Hint"

    Count lines in each file individually.

??? tip "Stronger Hint"

    Keep a running total.

??? tip "Almost There"

    Use:

    ```python
    len(contents.splitlines())
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("personal-todos.txt"),
        Path("work-todos.txt"),
        Path("project-todos.txt"),
    ]

    total_tasks = 0

    for path in paths:
        contents = path.read_text()
        total_tasks += len(contents.splitlines())

    print(total_tasks)
    ```

#### Why This Exercise Exists

Automation often involves aggregating information from multiple files.

This exercise demonstrates how content from several sources can be combined into a single result.

---

### PATHLIB-RF-19

#### Scenario

You maintain several meeting notes files.

You want to identify which files mention Python.

The files are:

```
- meeting-1.txt
- meeting-2.txt
- meeting-3.txt
```

#### Objective

Read each file and print the names of files that contain the word:

Python

#### Success Criteria

Your program should print only the matching filenames.

#### Need a Hint?

??? tip "Small Hint"

    Read the contents of each file first.

??? tip "Stronger Hint"

    Search for the keyword after reading the file.

??? tip "Almost There"

    Use:

    ```python
    "Python" in contents
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("meeting-1.txt"),
        Path("meeting-2.txt"),
        Path("meeting-3.txt"),
    ]

    for path in paths:
        contents = path.read_text()

        if "Python" in contents:
            print(path.name)
    ```

#### Why This Exercise Exists

Many practical tools search collections of files for keywords.

Examples include:

- Documentation search
- Log analysis
- Knowledge management systems
- Repository analysis tools

---

### PATHLIB-RF-20

#### Scenario

You are building a simple document inventory tool.

The tool should review a collection of text files and generate a report showing:

- Filename
- Character Count
- Line Count

#### Objective

Read multiple files and generate a summary for each file.

#### Success Criteria

Your program should produce output similar to:

```text
notes.txt
Characters: 124
Lines: 8

ideas.txt
Characters: 432
Lines: 21

tasks.txt
Characters: 98
Lines: 5
```

#### Need a Hint?

??? tip "Small Hint"

    Read each file one at a time.

??? tip "Stronger Hint"

    Generate a small report for every file.

??? tip "Almost There"

    Combine:

    ```python
    path.name
    len(contents)
    len(contents.splitlines())
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("notes.txt"),
        Path("ideas.txt"),
        Path("tasks.txt"),
    ]

    for path in paths:
        contents = path.read_text()

        print(path.name)
        print(f"Characters: {len(contents)}")
        print(f"Lines: {len(contents.splitlines())}")
        print()
    ```

#### Why This Exercise Exists

This exercise combines the major capabilities learned throughout the Reading Files section:

- Reading file contents
- Working with text
- Counting characters
- Counting lines
- Processing multiple files

Many real-world automation tools begin by collecting information from numerous files before performing more advanced analysis or generating reports.