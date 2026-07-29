# pathlib - Inspecting Paths

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

Each stage builds on the previous one, gradually moving from understanding how paths are created to using path creation as part of practical automation tasks.

---

## **Discover**

Learn the fundamental capability.

These exercises introduce the core ideas behind inspecting paths with pathlib.

_**Goal:**_

👉 Learn the capability.

---

### PATHLIB-IP-01

#### Scenario

You are building a note-taking application.

A user selects the file:

```
notes/meeting-notes.md
```

Before displaying information about the file, your application needs to know the filename.

#### Objective

Create a Path object representing:

```
notes/meeting-notes.md
```

Print only the filename.

#### Success Criteria

Your program should:

- Create a Path object
- Extract the filename
- Print the filename of `meeting-notes.md`


#### Need a Hint?

??? tip "Small Hint"

    Path objects contain information about a path.

    Explore the attributes available on a Path object.

??? tip "Stronger Hint"

    pathlib has an attribute that returns the final component of a path.

??? tip "Almost There"

    Use:

    ```python
    path.name
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/meeting-notes.md")

    print(path.name)
    ```

#### Why This Exercise Exists

Applications often need to display filenames to users.

Showing:

```
notes/meeting-notes.md
```

is usually less useful than showing:

```
meeting-notes.md
```

The `.name` attribute is one of the most commonly used pathlib inspection capabilities.

---

### PATHLIB-IP-02

#### Scenario

You are organizing files by type.

A file has the following path:

```
reports/annual-report.pdf
```

You need to determine what kind of file it is.

#### Objective

Create a Path object representing:

```
reports/annual-report.pdf
```

Print the file extension.

#### Success Criteria

Your program should:

- Create a Path object
- Extract the file extension
- Print:

.pdf

#### Need a Hint?

??? tip "Small Hint"

    File extensions typically appear after the final period.

??? tip "Stronger Hint"

    pathlib can extract the file extension for you.

??? tip "Almost There"

    Use:

    ```
    path.suffix
    ```

##### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("reports/annual-report.pdf")

    print(path.suffix)
    ```

##### Why This Exercise Exists

Many automation tasks depend on file types.

Examples include:

- Finding Python files
- Detecting image files
- Organizing downloads
- Filtering documents

The `.suffix` attribute provides a simple way to inspect file extensions.

---

### PATHLIB-IP-03

#### Scenario

You are generating a report title based on a filename.

The source file is:

```
reports/sales-2025.xlsx
```

You want the filename without the extension.

#### Objective

Create a Path object representing:

```
reports/sales-2025.xlsx
```

Print only the filename stem.

#### Success Criteria

Your program should:

- Create a Path object
- Extract the stem
- Print:

sales-2025

#### Need a Hint?

??? tip "Small Hint"

    The stem is the filename without the extension.

??? tip "Stronger Hint"

    pathlib provides a dedicated attribute for this.

??? tip "Almost There"

    Use:

    ```
    path.stem
    ```

##### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("reports/sales-2025.xlsx")

    print(path.stem)
    ```

##### Why This Exercise Exists

Many programs use filenames to generate:

- Report titles
- Log names
- Backup names
- Output filenames

The `.stem` attribute removes the extension automatically.

---

### PATHLIB-IP-04

#### Scenario

You are troubleshooting a configuration file.

Its location is:

```
config/settings.json
```

You need to identify which folder contains the file.

#### Objective

Create a Path object representing:

```
config/settings.json
```

Print the parent directory.

#### Success Criteria

Your program should:

- Create a Path object
- Print:

config

#### Need a Hint?

??? tip "Small Hint"

    Every file belongs to a directory.

??? tip "Stronger Hint"

    pathlib can identify the directory that contains a file.

??? tip "Almost There"

    Use:

    ```
    path.parent
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("config/settings.json")

    print(path.parent)
    ```

#### Why This Exercise Exists

Automation scripts often need to find related files near a target file.

The parent directory is frequently used when:

- Creating output files
- Loading configuration files
- Scanning project folders

---

### PATHLIB-IP-05

#### Scenario

Your application expects a configuration file named:

```
config.json
```

Before trying to read it, you want to verify that it exists.

#### Objective

Create a Path object representing:

```
config.json
```

Check whether the path exists.

Print:

File exists

or

File not found

#### Success Criteria

Your program should:

- Create a Path object
- Check whether the path exists
- Print an appropriate message

##### Need a Hint?

??? tip "Small Hint"

    Attempting to read a file that does not exist usually causes errors.

??? tip "Stronger Hint"

    pathlib provides a method that checks whether a path exists.

??? tip "Almost There"

    Use:

    ```
    path.exists()
    ```

##### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("config.json")

    if path.exists():
        print("File exists")
    else:
        print("File not found")
    ```

##### Why This Exercise Exists

Checking for existence is one of the most common filesystem tasks.

Responsible programs verify that files exist before attempting to use them.

---

## **Apply**

_Goal:_

👉 Use the capability.

---

### PATHLIB-IP-06

#### Scenario

You are building a simple document viewer.

Before opening a file, your application should verify that the file exists.

The file path is:

```
documents/project-plan.docx
```

If the file exists, print:

```
Document found
```

Otherwise print:

```
Document not found
```

#### Objective

Create a Path object and check whether the file exists.

#### Success Criteria

Your program should:

- Create a Path object
- Check whether the file exists
- Print either:
    - Document found
    - Document not found

#### Need a Hint?

??? tip "Small Hint"

    Applications should verify files exist before attempting to use them.

??? tip "Stronger Hint"

    pathlib provides a method that checks whether a path exists.

??? tip "Almost There"

    Use:

    path.exists()

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("documents/project-plan.docx")

    if path.exists():
        print("Document found")
    else:
        print("Document not found")
    ```

#### Why This Exercise Exists

Many real-world programs fail because they assume files exist.

Checking existence before working with a file is a simple but important habit that helps create more reliable software.

---

### PATHLIB-IP-07

#### Scenario

A user provides a path to your application.

Your program needs to determine whether the path points to:

- a file
- a directory

The path should be inspected and an appropriate message displayed.

#### Objective

Create a Path object and determine whether it represents a file or directory.

#### Success Criteria

Your program should print one of:

- File
- Directory
- Path does not exist

#### Need a Hint?

??? tip "Small Hint"

    Files and directories are both represented by Path objects.

??? tip "Stronger Hint"

    pathlib provides methods for checking what kind of path you're working with.

??? tip "Almost There"

    Explore:

    path.is_file()

    and

    path.is_dir()

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("documents")

    if not path.exists():
        print("Path does not exist")
    elif path.is_file():
        print("File")
    elif path.is_dir():
        print("Directory")
    ```

#### Why This Exercise Exists

Programs often behave differently depending on the type of path they receive.

For example:

- Files might be opened
- Directories might be scanned

Being able to identify the path type is an essential inspection capability.

---

### PATHLIB-IP-08

#### Scenario

You are organizing files in a Downloads folder.

For each file, you want to display the filename and its file type.

The path is:

```
downloads/vacation-photo.jpg
```

#### Objective

Create a Path object and display:

- Filename
- Extension

#### Success Criteria

Your program should print:

```text
Filename: vacation-photo.jpg
Extension: .jpg
```

#### Need a Hint?

??? tip "Small Hint"

    A Path object knows both its name and extension.

??? tip "Stronger Hint"

    These pieces of information are available as attributes.

??? tip "Almost There"

    Use:

    path.name

    and

    path.suffix

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("downloads/vacation-photo.jpg")

    print(f"Filename: {path.name}")
    print(f"Extension: {path.suffix}")
    ```

#### Why This Exercise Exists

Many automation tasks start by identifying the type of file being processed.

Examples include:

- Organizing downloads
- Processing images
- Filtering documents
- Scanning projects

---

### PATHLIB-IP-09

#### Scenario

You are creating a backup utility.

Before creating a backup, you want to determine where the original file is located.

The file path is:

```
projects/inventory/data.json
```

##### Objective

Display the directory that contains the file.

##### Success Criteria

Your program should print:

```text
projects/inventory
```

##### Need a Hint?

??? tip "Small Hint"

    Files always belong to a directory.

??? tip "Stronger Hint"

    pathlib can identify the directory containing a file.

??? tip "Almost There"

    Use:

    ```
    path.parent
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("projects/inventory/data.json")

    print(path.parent)
    ```

##### Why This Exercise Exists

Many programs need to locate files relative to other files.

Knowing the parent directory is useful when:

- Creating backups
- Saving reports
- Loading related files
- Generating output

---

### PATHLIB-IP-10

#### Scenario

You are inspecting files inside a software project.

You discover the following file:

```
src/main.py
```

You want to quickly learn more about it.

#### Objective

Display:

- Filename
- Filename without extension
- Extension
- Parent directory

#### Success Criteria

Your program should print:

```text
Filename: main.py
Stem: main
Extension: .py
Parent: src
```

#### Need a Hint?

??? tip "Small Hint"

    A Path object exposes several useful inspection attributes.

??? tip "Stronger Hint"

    Think about the attributes you've already learned for inspecting paths.

??? tip "Almost There"

    Use:

    - path.name
    - path.stem
    - path.suffix
    - path.parent

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("src/main.py")

    print(f"Filename: {path.name}")
    print(f"Stem: {path.stem}")
    print(f"Extension: {path.suffix}")
    print(f"Parent: {path.parent}")
    ```

#### Why This Exercise Exists

When exploring an unfamiliar project, developers frequently inspect files to understand:

- What the file is called
- What type of file it is
- Where it is located

This exercise combines several inspection capabilities into a practical workflow.

---

## **Compose**

_Goal:_

👉 Combine capabilities.

---

### PATHLIB-IP-11

#### Scenario

You join a new software project and are given the following file:

```
src/main.py
```

Before making any changes, you want to quickly learn more about it.

#### Objective

Create a Path object and display:

- Filename
- Filename without extension
- Extension
- Parent directory

#### Success Criteria

Your program should print:

```text
Filename: main.py
Stem: main
Extension: .py
Parent: src
```

#### Need a Hint?

??? tip "Small Hint"

    A Path object can provide several pieces of information about a file.

??? tip "Stronger Hint"

    Think about the inspection attributes you've already learned.

??? tip "Almost There"

    Use:

    - path.name
    - path.stem
    - path.suffix
    - path.parent

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("src/main.py")

    print(f"Filename: {path.name}")
    print(f"Stem: {path.stem}")
    print(f"Extension: {path.suffix}")
    print(f"Parent: {path.parent}")
    ```

#### Why This Exercise Exists

Developers frequently inspect files when exploring unfamiliar projects.

This exercise combines several inspection capabilities into a single useful report.

---

### PATHLIB-IP-12

#### Scenario

You are building a file upload system.

The application only accepts text files.

A user uploads a file and your program must determine whether it should be accepted.

#### Objective

Create a Path object and inspect its extension.

If the file ends with:

```
.txt
```

print:

```
Accepted
```

Otherwise print:

```
Rejected
```

#### Success Criteria

Your program should:

- Create a Path object
- Inspect the file extension
- Print:
    - Accepted
    - Rejected

#### Need a Hint?

??? tip "Small Hint"

    File extensions help determine file types.

??? tip "Stronger Hint"

    Compare the file extension against ".txt".

??? tip "Almost There"

    Use:

    ```
    path.suffix
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes.txt")

    if path.suffix == ".txt":
        print("Accepted")
    else:
        print("Rejected")
    ```

#### Why This Exercise Exists

Many applications inspect files before processing them.

Examples include:

- Upload validation
- Image processing
- Document management
- Security checks

File extensions are often the first piece of information examined.

---

### PATHLIB-IP-13

#### Scenario

You are reviewing files that belong to a project.

You want to generate a short summary showing:

- What the file is called
- What type of file it is
- Whether the file exists

#### Objective

Create a Path object and display:

- Filename
- Extension
- Exists

#### Success Criteria

Your output should look similar to:

```text
Filename: README.md
Extension: .md
Exists: True
```

#### Need a Hint?

??? tip "Small Hint"

    Combine multiple inspection capabilities in a single report.

??? tip "Stronger Hint"

    You'll need information about both the file itself and its existence.

??? tip "Almost There"

    Use:

    ```
    - path.name
    - path.suffix
    - path.exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("README.md")

    print(f"Filename: {path.name}")
    print(f"Extension: {path.suffix}")
    print(f"Exists: {path.exists()}")
    ```

#### Why This Exercise Exists

Real applications often gather several pieces of information about a file before deciding what to do next.

Inspection capabilities become much more useful when combined together.

---

### PATHLIB-IP-14

#### Scenario

You are creating a diagnostics tool.

Users frequently provide incorrect paths, so your application should explain what kind of path was supplied.

#### Objective

Create a Path object and print:

- Whether the path exists
- Whether it is a file
- Whether it is a directory

#### Success Criteria

Your program should display information similar to:

```text
Exists: True
File: False
Directory: True
```

#### Need a Hint?

??? tip "Small Hint"

    A Path object can tell you more than whether it exists.

??? tip "Stronger Hint"

    Explore the methods used to identify files and directories.

??? tip "Almost There"

    Use:

    ```
    - path.exists()
    - path.is_file()
    - path.is_dir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("documents")

    print(f"Exists: {path.exists()}")
    print(f"File: {path.is_file()}")
    print(f"Directory: {path.is_dir()}")
    ```

#### Why This Exercise Exists

Programs often need to inspect a path before deciding how it should be handled.

A diagnostics report like this can help identify incorrect or unexpected paths.

---

### PATHLIB-IP-15

#### Scenario

You are building a project inventory tool.

The tool should inspect a file and generate a short profile describing it.

The file path is:

```
config/settings.json
```

#### Objective

Create a Path object and display:

- Filename
- Stem
- Extension
- Parent Directory
- Exists

#### Success Criteria

Your program should produce a report similar to:

```text
Filename: settings.json
Stem: settings
Extension: .json
Parent: config
Exists: True
```

#### Need a Hint?

??? tip "Small Hint"

    This exercise combines almost everything you've learned about inspecting paths.

??? tip "Stronger Hint"

    Think about which Path attributes provide information about names, locations, and file types.

??? tip "Almost There"

    Use:

    ```
    - path.name
    - path.stem
    - path.suffix
    - path.parent
    - path.exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("config/settings.json")

    print(f"Filename: {path.name}")
    print(f"Stem: {path.stem}")
    print(f"Extension: {path.suffix}")
    print(f"Parent: {path.parent}")
    print(f"Exists: {path.exists()}")
    ```

#### Why This Exercise Exists

This exercise brings together the core inspection capabilities provided by pathlib.

Many real-world tools begin by inspecting a path and building a profile before performing further actions such as reading, writing, copying, or organizing files.

---

## **Automate**

_Goal:_

👉 Automate solutions.

---

### PATHLIB-IP-16

#### Scenario

Your Downloads folder contains several files.

Before organizing them, you want to quickly identify the type of each file.

The paths are:

```
- downloads/report.pdf
- downloads/photo.jpg
- downloads/notes.txt
```

#### Objective

Create Path objects for each file and display:

- Filename
- Extension

#### Success Criteria

Your program should produce output similar to:

```text
report.pdf -> .pdf
photo.jpg -> .jpg
notes.txt -> .txt
```

#### Need a Hint?

??? tip "Small Hint"

    Store the paths in a collection and process them one at a time.

??? tip "Stronger Hint"

    A loop can help you avoid repeating code.

??? tip "Almost There"

    Use:

    ```
    - path.name
    - path.suffix
    ```

    inside a loop.

##### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("downloads/report.pdf"),
        Path("downloads/photo.jpg"),
        Path("downloads/notes.txt"),
    ]

    for path in paths:
        print(f"{path.name} -> {path.suffix}")
    ```

##### Why This Exercise Exists

Automation often starts by inspecting many files rather than just one.

This exercise demonstrates how path inspection can be applied repeatedly across a collection of files.

---

### PATHLIB-IP-17

#### Scenario

You maintain a project that contains many different file types.

You want a quick overview of the project contents.

The paths are:

```
- README.md
- requirements.txt
- src/main.py
- config/settings.json
```

##### Objective

Generate a report showing:

- Filename
- Extension
- Parent Directory

##### Success Criteria

Your program should produce output similar to:

```text
README.md | .md | .
requirements.txt | .txt | .
main.py | .py | src
settings.json | .json | config
```

##### Need a Hint?

??? tip "Small Hint"

    Multiple pieces of information can be extracted from each Path object.

??? tip "Stronger Hint"

    Generate one line of output for each path.

??? tip "Almost There"

    Use:

    ```
    - path.name
    - path.suffix
    - path.parent
    ```

##### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("README.md"),
        Path("requirements.txt"),
        Path("src/main.py"),
        Path("config/settings.json"),
    ]

    for path in paths:
        print(f"{path.name} | {path.suffix} | {path.parent}")
    ```

##### Why This Exercise Exists

Developers frequently inspect many files when exploring unfamiliar projects.

Generating summaries helps reveal the structure of a codebase quickly.

---

### PATHLIB-IP-18

#### Scenario

You are reviewing files before archiving a project.

Some files may have been deleted over time.

Before creating the archive, you want to know which files still exist.

#### Objective

Create several Path objects and display whether each file exists.

#### Success Criteria

Your program should produce output similar to:

```text
README.md -> True
notes.txt -> False
config.json -> True
```

#### Need a Hint?

??? tip "Small Hint"

    You'll need to inspect each path individually.

??? tip "Stronger Hint"

    pathlib provides a method for determining whether a path exists.

??? tip "Almost There"

    Use:

    ```
    path.exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("README.md"),
        Path("notes.txt"),
        Path("config.json"),
    ]

    for path in paths:
        print(f"{path} -> {path.exists()}")
    ```

#### Why This Exercise Exists

Before processing files, many automation tools verify that the expected files are actually present.

This reduces errors and helps identify missing resources.

---

### PATHLIB-IP-19

#### Scenario

You are building a document processing system.

The system should only process PDF files.

Before continuing, you need to identify which files are PDF documents.

The paths are:

```
- report.pdf
- notes.txt
- budget.xlsx
- manual.pdf
```

#### Objective

Inspect each file and print only the PDF files.

#### Success Criteria

Your program should print:

```text
report.pdf
manual.pdf
```

#### Need a Hint?

??? tip "Small Hint"

    Examine the file extension.

??? tip "Stronger Hint"

    Process each file in a loop.

??? tip "Almost There"

    Compare:

    ```
    path.suffix
    ```

    against:

    ```
    .pdf
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("report.pdf"),
        Path("notes.txt"),
        Path("budget.xlsx"),
        Path("manual.pdf"),
    ]

    for path in paths:
        if path.suffix == ".pdf":
            print(path.name)
    ```

#### Why This Exercise Exists

Many automation tools classify files before processing them.

Extension-based filtering is commonly used when working with documents, images, source code, and data files.

---

### PATHLIB-IP-20

#### Scenario

You are creating a simple file inventory tool.

The tool should inspect every path it receives and generate a useful summary.

##### Objective

For each path, display:

```
- Filename
- Stem
- Extension
- Parent Directory
- Exists
```

#### Success Criteria

Your program should generate a report similar to:

```text
Filename: main.py
Stem: main
Extension: .py
Parent: src
Exists: True
```

for each path being inspected.

#### Need a Hint?

??? tip "Small Hint"

    Combine all of the inspection capabilities you've learned so far.

??? tip "Stronger Hint"

    Generate a complete profile for each path.

??? tip "Almost There"

    Use:

    ```
    - path.name
    - path.stem
    - path.suffix
    - path.parent
    - path.exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("src/main.py"),
        Path("config/settings.json"),
        Path("README.md"),
    ]

    for path in paths:
        print(f"Filename: {path.name}")
        print(f"Stem: {path.stem}")
        print(f"Extension: {path.suffix}")
        print(f"Parent: {path.parent}")
        print(f"Exists: {path.exists()}")
        print()
    ```

#### Why This Exercise Exists

This exercise combines the core inspection capabilities into a practical automation task.

Many real-world tools begin by gathering information about files before reading, modifying, copying, moving, or organizing them.

This exercise acts as a capstone for the Inspecting Paths capability and prepares learners for upcoming topics such as Reading Files, Finding Files, and Directory Operations.