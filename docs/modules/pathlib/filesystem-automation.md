# pathlib - Filesystem Automation

## Overview

Filesystem automation is where the capabilities learned throughout the pathlib module come together.

Earlier capabilities focused on individual tasks:

- Creating paths
- Inspecting paths
- Reading files
- Writing files
- Finding files
- Manipulating paths
- Working with directories

Real-world programs rarely perform only one of these operations.

Instead, they combine many filesystem capabilities to solve practical problems.

Examples include:

- Organizing files
- Generating reports
- Creating backups
- Processing directories of data
- Building repository analysis tools
- Managing documentation

Filesystem automation is the process of combining multiple pathlib capabilities to reduce repetitive work and create useful tools.

This capability represents the culmination of everything learned in the pathlib module.

## Learning Progression

The exercises in this capability are organized into four stages:

```text
Discover
    ↓
Apply
    ↓
Compose
    ↓
Automate
```

Each stage builds on the previous one, gradually moving from understanding automation concepts to building practical filesystem tools.

---

## Discover

Learn the fundamental capability.

These exercises introduce simple automations that combine multiple pathlib capabilities.

Goal:

👉 Learn the capability.

---

### PATHLIB-FA-01

#### Scenario

You have a directory containing many different files.

Before performing any processing, you would like to identify all text files in the directory.

This is often the first step in an automation workflow.

#### Objective

Create a program that:

- Creates a Path object representing `notes`
- Finds all `.txt` files in the directory
- Prints each file path

#### Success Criteria

Your program should:

- Create a Path object
- Find text files
- Print every matching file

#### Need a Hint?

??? tip "Small Hint"

    Start by creating a Path object for the directory.

??? tip "Stronger Hint"

    pathlib provides methods for searching files that match a pattern.

??? tip "Almost There"

    Use:

    ```python
    path.glob("*.txt")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    for file in notes.glob("*.txt"):
        print(file)
    ```

#### Why This Exercise Exists

Many automation tools begin by discovering files before doing anything else.

Examples include:

- Note processing tools
- Import utilities
- Data processing scripts
- Backup systems

This exercise combines path creation and file discovery into a simple automation workflow.

---

### PATHLIB-FA-02

#### Scenario

You maintain a collection of Markdown documents.

You would like a quick overview of how many notes currently exist.

Instead of counting files manually, you decide to automate the process.

#### Objective

Create a program that:

- Creates a Path object representing `notes`
- Finds all Markdown files
- Prints the total number found

#### Success Criteria

Your program should:

- Search for Markdown files
- Count the results
- Display the total count

#### Need a Hint?

??? tip "Small Hint"

    Finding files and counting files are two separate steps.

??? tip "Stronger Hint"

    Consider storing the search results before calculating the count.

??? tip "Almost There"

    Convert the search results to a list and use:

    ```python
    len(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    markdown_files = list(
        notes.rglob("*.md")
    )

    print(
  *     f"Markdown files: {len(markdo*n_files)}"
    )
    ```

#### Why *his Exercise Exists

Automation of*en involves gathering information *ather than changing files.

Exampl*s include:

- Repository analysis
* Content audits
- Documentation re*orting
- Workspace summaries

This*exercise introduces simple filesys*em reporting.

---

### PATHLIB-FA-*3

#### Scenario

You are exploring*a project directory and want a qui*k inventory of its contents.

You *ould like to know:

- The file nam*
- The file extension

for every f*le discovered.

#### Objective

Cre*te a program that:

- Searches for*all files inside `project`
- Print* the file name
- Prints the file e*tension

#### Success Criteria

You* program should:

- Find files
- Access file information
- Print useful details about each file

#### Need a Hint?

??? tip "Small Hint"

    A discovered file is still a Path object.

??? tip "Stronger Hint"

    Path objects provide attributes describing the file.

??? tip "Almost There"

    Use:

    ```python
    file.name
    file.suffix
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    for file in project.rglob("*"):
        if file.is_file():
            print(
                f"{file.name} ({file.suffix})"
            )
    ```

#### Why This Exercise Exists

Many automation tasks begin by building an inventory of files.

Examples include:

- Repository scanners
- File organizers
- Content analysis tools
- Documentation systems

This exercise combines file discovery and path inspection.

---

### PATHLIB-FA-04

#### Scenario

A reporting tool stores output inside:

```text
reports/
```

Before generating reports, the program should ensure the directory exists.

If it is missing, the program should create it automatically.

#### Objective

Create a program that:

- Creates a Path object representing `reports`
- Checks whether the directory exists
- Creates it if necessary

#### Success Criteria

Your program should:

- Check existence
- Create missing directories
- Print a confirmation message

#### Need a Hint?

??? tip "Small Hint"

    You may need an if statement.

??? tip "Stronger Hint"

    Check whether the directory exists before creating it.

??? tip "Almost There"

    Combine:

    ```python
    exists()
    ```

    and:

    ```python
    mkdir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    reports = Path("reports")

    if not reports.exists():
        reports.mkdir()

    print("Reports directory ready")
    ```

#### Why This Exercise Exists

Many automation tools need to prepare their environment before doing work.

Examples include:

- Backup tools
- Report generators
- Documentation systems
- Build scripts

This exercise combines inspection and directory creation.

---

### PATHLIB-FA-05

#### Scenario

Your project directory contains many files.

You want to identify files larger than 1 MB, since large files may need to be reviewed before committing them to version control.

#### Objective

Create a program that:

- Searches all files inside `project`
- Finds files larger than 1 MB
- Prints the matching file paths

#### Success Criteria

Your program should:

- Search recursively
- Inspect file metadata
- Filter files by size
- Print matching files

#### Need a Hint?

??? tip "Small Hint"

    You will need information about each file after finding it.

??? tip "Stronger Hint"

    Path objects can provide file metadata.

??? tip "Almost There"

    Use:

    ```python
    file.stat().st_size
    ```

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

Real filesystem automation often combines multiple capabilities:

- Finding files
- Inspecting files
- Filtering results
- Reporting findings

This exercise represents a small but useful automation that resembles real maintenance and repository analysis tools.

---

## Apply

Use the capability in realistic situations.

These exercises reinforce automation techniques through practical scenarios.

Goal:

👉 Use the capability.

---

### PATHLIB-FA-06

#### Scenario

You maintain a knowledge base containing Markdown documentation spread across many folders.

Before publishing or reviewing the documentation, you want a report showing every Markdown file and its location.

#### Objective

Create a program that:

- Searches the `docs` directory recursively
- Finds all Markdown files
- Prints the file name
- Prints the parent directory

#### Success Criteria

Your program should:

- Search recursively
- Find Markdown files
- Display file names
- Display parent directories

#### Need a Hint?

??? tip "Small Hint"

    Each discovered file is a Path object.

??? tip "Stronger Hint"

    Path objects contain information about both the file name and its location.

??? tip "Almost There"

    Use:

    ```python
    file.name
    file.parent
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    docs = Path("docs")

    for file in docs.rglob("*.md"):
        print(f"File: {file*name}")
        print(f"Folder: {f*le.parent}")
        print()
    ```

#### Why This Exercise Exists

Documentation systems often need inventory reports before content can be reviewed, reorganized, or published.

This exercise combines:

- Finding files
- Inspecting paths
- Reporting information

into a practical automation task.

---

### PATHLIB-FA-07

#### Scenario

You have cloned an unfamiliar repository and want to understand its structure.

You would like to know:

- Which top-level directories exist
- How many directories were found

#### Objective

Create a program that:

- Examines a directory named `repository`
- Lists all immediate subdirectories - Displays the total number of directories

#### Success Criteria

Your program should:

- Iterate through directory contents
- Identify directories
- Count directories
- Print a summary

#### Need a Hint?

??? tip "Small Hint"

    Start by examining everything inside the repository directory.

??? tip "Stronger Hint"

    Filter the results so that only directories remain.

??? tip "Almost There"

    Use:

    ```python
    item.is_dir()
    ```

    when looping through:

    ```python
    repository.iterdir()
    ```

#### Solution

??? success "Show solution"

    ```python
    from pathlib import Path

    repository = Path("repository")

    directories = [
        item
        for item in repository.iterdir()
        in item.is_dir()
    ]

    for directory in directories:
        print(directory.name)

    print(
       f"\nTotal directories: {len(directories)}"
    )
    ```

#### Why This Exercise Exists

Developers frequently need a quick overview of a project before making changes.

This exercise combines:

- Directory traversal
- Directory inspection
- Reporting

to produce a useful repository summary.

---

### PATHLIB-FA-08

#### Scenario

You are preparing a project report.

You want to know how many files of each major type exist in the repository:

- Python files
- Markdown files
- JSON files

#### Objective

Create a program that:

- Searches the `project` directory recursively
- Counts all `.py` files
- Counts all `.md` files
- Counts all `.json` files
- Prints a report

#### Success Criteria

Your program should:

- Search recursively
- Count multiple file types
- Display a summary report

#### Need a Hint?

??? tip "Small Hint"

    Each file type can be searched independently.

??? tip "Stronger Hint"
    Store the search results before counting them.

??? tip "Almost There"

    Use:

    ```python
    len(...)
    ```

    on each collection of matching files.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    python_files = list(project.rglob("*.py"))
    markdown_files = list(project.rglob("*.md"))
    json_files = list(project.rglob("*.json"))

    print(f"Python files: {len(python_files)}")
    print(f"Markdown files: {len(markdown_files)}*)
    print(f"JSON files: {len(json_files)}")
    ```

#### Why This Exercise Exists

Repository summaries are often the first step in understanding a codebase.

This exercise combines:

- Recursive searching
- File filtering
- Counting
- Reporting

into a small but practical analysis tool.

---

### PATHLIB-FA-09

#### Scenario

You are creating a b*ckup planning tool.

Before copyin* any files, you want to calculate where backup files should be stored.

For example:

```text
notes/todo.txt
```

should become:

```text
backups/todo.txt
```

#### Objective
Create a program that:

- Finds all `.txt` files in `notes`
- Creates a corresponding backup path inside `backups`
- Prints both paths

#### Success Criteria

Your program should:

- Find files
- Generate new paths
- Preserve the original filename
- Print the original and backup paths

#### Need a Hint?

??? tip "Small Hint"

    The backup path uses information from the original file.

??? tip "Stronger Hint"

    The file name remains unchanged.

??? tip "Almost There"

    Combine:

    ```python
    Path("backups")
    ```

    with:

    ```python
    file.name
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Pat*

    notes = Path("notes")

    for file in notes.rglob("*.txt"):
        backup = Path("backups") / file.name

        print(f"Original: {file}")
        print(f"Backup:   {backup}")
        print()
    ```

#### Why This Exercise Exists

Many automation tools create new paths based on files they discover.

Examples include:

- Backup systems
- Build systems
- Export tools
- Deplo*ment scripts

This exercise combines file discovery and path generation.

---

### PATHLIB-FA-10

#### Scenario

You maintain a large collection of Markdown notes.

You would like a report showing:

- How many notes exist
- Which note has the longest filename

#### Objective

Creat* a program that:

- Searches `notes` recursively
- Finds all Markdown files
- Counts the files
- Identifies the file with the longest filename
- Prints the results

#### Succe*s Criteria

Your program should:

- Search recursively
- Count files
- Compare filenames
- Print a summary report

#### Need a Hint?

??? tip "Small Hint"

    Start by gather*ng all Markdown files.

??? tip "Stronger Hint"

    Store the results in a list so they can be reused.

??? tip "Almost There"

    Use:

    ```python
    max(...)
    ```
    
    with:

    ```python
    key=lambda file: len(file.name)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    markdown_files = list(
        notes.rglob("*.md")
    )

    longest_name = max(
        markdown_files,
        key=lambda file: len(file.name)
    )

    print(
        f"Total notes: {len(markdown_files)}"
    )

    print(
        f"Longest filename: {longest_name.name}"
    )
    ```

#### Why This Exercise Exists

Filesystem automation often involves gathering information from collections of files.

Examples include:

- Documentation audits
- Repository analysis
- Content reporting
- Workspace monitoring

This exercise combines several capabilities into a more realistic reporting workflow.

---

## Compose

Combine multiple techniques.

These exercises require bringing together ideas learned throughout the pathlib module.

Goal:

👉 Combine capabilities.

---

### PATHLIB-FA-11

#### Scenario

You maintain a documentation repository containing Markdown files spread across multiple folders.

Before publishing the documentation, you want to generate a detailed inventory showing:

- The file name
- The directory containing the file
- The file extension

#### Objective

Create a program that:

- Searches the `docs` directory recursively
- Finds all files
- Displays the filename
- Displays the parent directory
- Displays the file extension

#### Success Criteria

Your program should:

- Search recursively
- Find all files
- Display multiple pieces of information about each file
- Produce a readable report

#### Need a Hint?

??? tip "Small Hint"

    After finding a file, pathlib exposes useful information about it.

??? tip "Stronger Hint"

    Try combining file discovery with path inspection.

??? tip "Almost There"

    Use:

    ```python
    file.name
    file.parent
    file.suffix
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    docs = Path("docs")

    for file in docs.rglob("*"):
        if file.is_file():
            print(f"Name: {file.name*")
            print(f"Folder: {file.parent}")
            print*f"Extension: {file.suffix}")
            print())
    ```

#### Why This Exercise Exis*s

Many automation tools begin by *uilding inventories of available f*les.

Examples include*

- Documentation systems
- Conten* management tools
- Repository sca*ners
- Migration*utilities

This exercise combines *ile discovery, path inspection, an* reporting.

---

##*PATHLIB-FA-12

*### Scenario

You are*exploring a*source code repository.

You would*like to identify*all Python files and see where*they are located.

In addition, yo**want to know how many Python files*the repository contains.

#### Obje*tive

Create a program that:

- Se*rches the `src* directory recursively
- Finds all*Python files
- Prints*each file path
* Displays the total number*of Python files

###*Success*Criteria

Your program should:

- *earch recursively
- Filter by file*type
- Display matching files
- Di*play a summary count*

#### Need a Hint?

??? tip*"Small Hint"

    First*gather*all matching files.

??? tip "*tronger Hint"

    The*same*collection can be used for both*printing and counting.

??? tip "*lmost*There"

    Store the results*using:

    ```python
   *list*path.rglob("*.py"))
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    src = Path("src")

    python_files = list(
        src.rglob("*.py")
    )

    for file*in python_files:
        print(fil*)

*   print(
        f*\nTotal Python files:*{len(python_files)}"
*   )
    ```

#### Why This*Exercise Exists

Repository analys*s often*involves discovering files and sum*arizing what was found.

This exer*ise combines:

* Recursive searching
- Filtering
* Reporting
- Counting

into*a*realistic developer workflow.

---

### PATHLIB-FA-13

#### Scenario

You maintain*a*collection of datasets.

Before be*inning*analysis, you want to understand w*at data files exist and where they*are stored.

The datasets use CSV *iles.

#### Objective

*reate a program that:

- Searches*the*`data` directory recursively*- Finds all CSV files
* Prints the file name
-*Prints*the parent*directory
- Displays*the total*number of CSV*files

#### Success*Criteria

*our program should:

- Search recu*sively
- Filter CSV files*- Report*file locations
* Provide a summary count

###*Need*a Hint?

??? tip "Small*Hint"

    Each*file contains*information about both its name an* location.

??? tip "Stronger Hint*

    Store*the matching*files before producing the summary*

??? tip "Almost There"

   *Combine*

    ```python
    file*name
    file*parent
*   len(...)
    ```

###*Solution*
??? success "Show Solution*

    ```python
    from pathlib i*port Path

    data*=*Path("data")

    csv_files*= list(
        data*r*lob("*.csv")
    )

    for file in csv_files:
        print(f"File: {file.name}")
        print(f"Folder: {file.parent}")
        print()

    print(
        f"Total CSV files: {len(csv_files)}"
    )
    ```

#### Why This Exercise Exists

Many analysis workflows start by exploring available datasets.

This exercise combines:

- File discovery
- File filtering
- Path inspection
- Summary reporting

to create a useful inventory tool.

---

### PATHLIB-FA-14

#### Scenario

You are reviewing a project before sharing it with a teammate.

You would like a quick health report showing:

- Number of Python files
- Number of Markdown files
- Number of JSON files
- Number of directories

#### Objective

Create a program that scans a directory named `project` and generates a summary report.

#### Success Criteria

Your program should:

- Search recursively
- Count multiple file types
- Count directories
- Display a readable report

#### Need a Hint?

??? tip "Small Hint"

    Different file types can be searched separately.

??? tip "Stronger Hint"

    Directories can be counted using directory inspection methods.

??? tip "Almost There"

    Consider using:

    ```python
    item.is_dir()
    ```

    when iterating through discovered paths.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    python_files = list(project.rglob("*.py"))
    markdown*files*= list(project.r*lob("*.md"))
    json_files = list(project.rglob("*.json"))

    directories*=*[
        item
        for item in project.rglob("*")
        if item.is_dir()
    ]

    print(f"Python files: {len(python_files)}")
    print(f"Markdown files: {len(markdown_files)}")
    print(f"JSON files: {len(json_files)}")
    print(f"Directories: {len(directories)}")
    ```

#### Why This Exercise Exists

Many development tools generate summary reports to help developers understand a project.

Examples include:

- Repository scanners
- Documentation analyzers
- Health-check tools
- Migration assessment tools

This exercise combines multiple pathlib capabilities into a single reporting workflow.

---

### PATHLIB-FA-15

#### Scenario

You are building a static site generator.

Markdown files are stored inside:

```text
content/
```

The generated HTML files should eventually live inside:

```text
site/
```

Before creating the HTML files, you want to generate a plan showing:

- Source file
- Destination file

#### Objective

Create a program that:

- Finds all Markdown files inside `content`
- Generates corresponding HTML paths
- Displays both source and destination paths

#### Success Criteria

Your program should:

- Search recursively
- Generate new output paths
- Change file extensions
- Produce a readable report

#### Need a Hint?

??? tip "Small Hint"

    The destination path depends on the source file.

??? tip "Stronger Hint"

    The filename remains the same while the extension changes.

??? tip "Almost There"

    Combine:

    ```python
    file.with_suffix(".html")
    ```

    with:

    ```python
    Path("site")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    content = Path("content")

    for file in content.rglob("*.md"):
        output =*(
            Path*"site")
*           / file.with_suffix(".*tml").name
        )

*      *print(f"Source:*{file}")
        print(f*Output: {output}")
*       print()
    ```

#### Why This Exercise Exists

*eal automation workflows often inv*lve*planning work before performing it*

Examples include:

- Static site*generators
- Build*tools*- Export systems
* Deployment pipelines

This exerci*e combines*file discovery, path manipulation* and reporting into a workflow*that resembles a real production t*ol.

---

## Automate

Create solutions that reduce repetitive work.

These exercises focus on building practical automations that resemble real tools.

Goal:

👉 Automate solutions.

---

### PATHLIB-FA-16

#### Scenario

Your Downloads folder has become cluttered with many different file types.

Before organizing the files, you want to generate a report showing:

- Text files
- Images
- PDFs

and how many of each exist.

#### Objective

Create a program that:

- Searches a directory named `downloads`
- Counts `.txt` files
- Counts `.jpg` files
- Counts `.pdf` files
- Prints a summary report

#### Success Criteria

Your program should:

- Search recursively
- Group files by type
- Count files
- Display a readable report

#### Need a Hint?

??? tip "Small Hint"

    Search for each file type separately.

??? tip "Stronger Hint"

    Store matching files in lists before counting them.

??? tip "Almost There"

    Use:

    ```python
    len(...)
    ```

    on each collection of matching files.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    downloads = Path("downloads")

    text_files = list(downloads.rglob("*.txt"))
    image_files = list(downloads.rglob("*.jpg"))
    pdf_files = list(downloads.rglob("*.pdf"))

    print(f"Text *iles: {len(text_files)}")
    print(f"Images: {len(image_files)}")
    print(f"PDFs: {len(pdf_files)}")
    ```

#### Why This Exercise Exis*s

Many automation tools begin by *nalyzing files before taking actio*.

Examples include:

- Downloads *rganizers
- Cleanup tools
- Reposi*ory scanners
- Backup utilities

T*is exercise combines file discover*, filtering, counting, and reporti*g.

---

### PATHLIB-FA-17

#### Sce*ario

You are preparing to back up*important documents.

Before copyi*g anything, you want a report show*ng:

- Every Markdown file that wi*l be backed up
- The backup locati*n for each file

#### Objective

Cr*ate a program that:

- Finds all M*rkdown files in `notes`
- Generate* a corresponding path inside `back*ps`
- Prints both the source path *nd backup path

#### Success Criter*a

Your program should:

- Search *ecursively
- Generate backup paths*- Preserve filenames
- Print a bac*up plan

#### Need a Hint?

??? tip*"Small Hint"

    The backup locat*on uses the original filename.

??* tip "Stronger Hint"

    Create a*new path inside the backup directo*y.

??? tip "Almost There"

    Us*:

    ```python
    Path("backups*) / file.name
    ```

#### Solutio*

??? success "Show Solution"

   *```python
    from pathlib import *ath

    notes = Path("notes")

  * for file in notes.rglob("*.md"):
*       backup_path = Path("backups*) / file.name

        print(f"Sou*ce: {file}")
        print(f"Backu*: {backup_path}")
        print()
*   ```

#### Why This Exercise Exis*s

Many automation workflows invol*e planning operations before perfo*ming them.

Examples include:

- B*ckup systems
- Deployment tools
- *igration utilities
- Build pipelin*s

This exercise combines file dis*overy and path generation into a u*eful planning tool.

---

### PATHL*B-FA-18

#### Scenario

You want a *uick overview of a Python reposito*y.

The report should show:

- Num*er of Python files
- Number of Mar*down files
- Number of JSON files
* Number of directories

#### Object*ve

Create a repository scanner th*t generates a summary report for a*directory named:

```text
reposito*y
```

#### Success Criteria

Your *rogram should:

- Search recursive*y
- Count multiple file types
- Co*nt directories
- Display a complet* summary

#### Need a Hint?

??? ti* "Small Hint"

    Different file *ypes can be counted independently.*
??? tip "Stronger Hint"

    Dire*tory counting requires filtering d*scovered paths.

??? tip "Almost T*ere"

    Use:

    ```python
    *tem.is_dir()
    ```

    when pro*essing discovered paths.

#### Solu*ion

??? success "Show Solution"

*   ```python
    from pathlib impo*t Path

    repository = Path("rep*sitory")

    python_files = list(*epository.rglob("*.py"))
    markd*wn_files = list(repository.rglob("*.md"))
    json_files = list(repos*tory.rglob("*.json"))

    directo*ies = [
        item
        for i*em in repository.rglob("*")
      * if item.is_dir()
    ]

    print*f"Python files: {len(python_files)*")
    print(f"Markdown files: {le*(markdown_files)}")
    print(f"JS*N files: {len(json_files)}")
    p*int(f"Directories: {len(directorie*)}")
    ```

#### Why This Exercis* Exists

Repository scanners are p*actical tools used by many develop*rs.

This exercise combines:

- Re*ursive searching
- File filtering
* Directory inspection
- Reporting
*into a realistic automation utilit*.

---

### PATHLIB-FA-19

#### Scen*rio

You maintain a documentation *ite built from Markdown files.

Be*ore publishing the site, you want * report showing:

- Source Markdow* file
- Destination HTML file

for*every page that will be generated.*
#### Objective

Create a program t*at:

- Searches `content`
- Finds *ll Markdown files
- Generates corr*sponding HTML paths in `site`
- Pr*nts both paths

#### Success Criter*a

Your program should:

- Search recursively
- Generate output paths
- Change file extensions
- Display the publishing plan

#### Need a Hint?

??? tip "Small Hint"

    The destination filename is based on the source filename.

??? tip "Stronger Hint"

    The extension changes from `.md` to `.html`.

??? tip "Almost There"

    Use:

    ```python
    file.with_suffix(".html")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    content = Path("content")

    for file in content.rglob("*.md"):
        output = (
            Path("site")
            / file.with_suffix(".html").name
        )

        print(f"Source: {file}")
        print(f"Output: {output}")
        print()
    ```

#### Why This Exercise Exists

Many automation tools generate files from source content.

Examples include:

- Static site generators
- Documentation systems
- Report generators
- Export pipelines

This exercise combines file discovery, path manipulation, and reporting.

---

### PATHLIB-FA-20

#### Scenario

You are building a filesystem dashboard.

The tool should provide a high-level overview of a project by displaying:

- Total files
- Total directories
- Number of Python files
- Number of Markdown files
- Largest file found

#### Objective

Create a program that scans a directory named:

```text
project
```

and generates a filesystem summary report.

#### Success Criteria

Your program should:

- Search recursively
- Count files
- Count directories
- Identify the largest file
- Display a complete report

#### Need a Hint?

??? tip "Small Hint"

    Store discovered files in a collection.

??? tip "Stronger Hint"

    The largest file can be determined using file size metadata.

??? tip "Almost There"

    Combine:

    ```python
    file.stat().st_size
    ```

    with:

    ```python
    max(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    files = [
        item
        for item in project.rglob("*")
        if item.is_file()
    ]

    directories = [
        item
        for item in project.rglob("*")
        if item.is_dir()
    ]

    largest_file = max(
        files,
        key=lambda file: file.stat().st_size
    )

    python_files = list(project.rglob("*.py"))
    markdown_files = list(project.rglob("*.md"))

    print(f"Total files: {len(files)}")
    print(f"Total directories: {len(directories)}")
    print(f"Python files: {len(python_files)}")
    print(f"Markdown files: {len(markdown_files)}")
    print(f"Largest file: {largest_file}")
    ```

#### Why This Exercise Exists

This exercise serves as the capstone of the entire pathlib module.

It combines:

- Path creation
- Path inspection
- File discovery
- Directory traversal
- Metadata inspection
- Counting
- Reporting

into a realistic utility that resembles the kind of exploratory tools developers build in real projects.

By this point, learners are no longer focusing on individual pathlib methods. They are using pathlib as a collection of capabilities to solve practical filesystem problems.