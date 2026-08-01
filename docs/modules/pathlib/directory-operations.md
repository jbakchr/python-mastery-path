# Directory Operations

## Overview

Directories are the containers that organize files on a filesystem.

Before files can be created, moved, archived, or processed, programs often need to work with directories first.

Common tasks include:

- Creating project folders
- Creating output directories
- Checking whether directories exist
- Traversing directory structures
- Preparing locations for generated files

The `pathlib` module makes directory operations straightforward by providing clear methods for working with directories as Path objects.

Mastering directory operations is an important step toward building reliable filesystem automation.

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

Each stage builds on the previous one, gradually moving from understanding a capability to using it in practical automation tasks.

---

## Discover

Learn the fundamental capability.

These exercises introduce the core ideas in a simple and focused way.

Goal:

👉 Learn the capability.

---

### PATHLIB-DO-01

#### Scenario

You are starting a new project and want a dedicated folder for your notes.

The folder does not exist yet.

Before you can save files there, you need to create it.

#### Objective

Create a directory named:

```text
notes
```

#### Success Criteria

Your program should:

- Create a Path object
- Create the directory if it does not already exist

#### Need a Hint?

??? tip "Small Hint"

    Path objects can represent both files and directories.

??? tip "Stronger Hint"

    pathlib provides a method for creating directories.

??? tip "Almost There"

    Use:

    ```python
    path.mkdir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    notes.mkdir()
    ```

#### Why This Exercise Exists

Many programs need to create directories before writing files.

Examples include:

- Notes applications
- Report generators
- Backup tools
- Export utilities

Creating directories is one of the most fundamental filesystem operations.

---

### PATHLIB-DO-02

#### Scenario

You are organizing a documentation project.

You want the following directory structure:

```text
docs/
└── guides/
```

Neither directory currently exists.

#### Objective

Create the directory structure:

```text
docs/guides
```

#### Success Criteria

Your program should:

- Create a Path object
- Create all required directories
- Create parent directories automatically

#### Need a Hint?

??? tip "Small Hint"

    The parent directory does not exist yet.

??? tip "Stronger Hint"

    pathlib can create missing parent directories automatically.

??? tip "Almost There"

    Use:

    ```python
    path.mkdir(parents=True)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    guides = Path("docs/guides")

    guides.mkdir(parents=True)
    ```

#### Why This Exercise Exists

Programs often need to create nested directory structures.

Examples include:

- Documentation systems
- Build pipelines
- Website generators
- Data exports

This capability allows complex directory structures to be created safely and efficiently.

---

### PATHLIB-DO-03

#### Scenario

Before generating a report, you want to check whether the output directory already exists.

The directory should be:

```text
reports
```

#### Objective

Create a `Path` object representing:

```text
reports
```

Check whether the directory exists and print the result.

#### Success Criteria

Your program should:

- Create a Path object
- Check whether the path exists
- Print the result

#### Need a Hint?

??? tip "Small Hint"

    Many filesystem operations begin with checking whether something already exists.

??? tip "Stronger Hint"

    Path objects provide a method for existence checks.

??? tip "Almost There"

    Use:

    ```python
    path.exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    reports = Path("reports")

    print(reports.exists())
    ```

#### Why This Exercise Exists

Before creating files or directories, programs often need to determine whether a location already exists.

Examples include:

- Setup scripts
- Installation tools
- Backup utilities
- Build systems

Existence checks help avoid unnecessary errors and duplicate work.

---

### PATHLIB-DO-04

#### Scenario

Your program receives a path from a user.

The path could represent:

- A file
- A directory

Before proceeding, your program needs to determine which it is.

The path is:

```text
documents
```

#### Objective

Create a `Path` object representing:

```text
documents
```

Check whether the path represents a directory and print the result.

#### Success Criteria

Your program should:

- Create a Path object
- Check whether the path is a directory
- Print the result

#### Need a Hint?

??? tip "Small Hint"

    Existence and type are not the same thing.

??? tip "Stronger Hint"

    pathlib has methods that check specific filesystem types.

??? tip "Almost There"

    Use:

    ```python
    path.is_dir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    documents = Path("documents")

    print(documents.is_dir())
    ```

#### Why This Exercise Exists

Programs frequently need to distinguish between files and directories.

Examples include:

- File explorers
- Backup tools
- Search utilities
- Repository scanners

Being able to identify directories is a key filesystem capability.

---

### PATHLIB-DO-05

#### Scenario

You are exploring a project and want to understand its structure.

The project contains several subdirectories, such as:

```text
project/
├── src/
├── tests/
├── docs/
└── scripts/
```

You want to list only the directories.

#### Objective

Create a `Path` object representing:

```text
project
```

Print all immediate subdirectories contained within the directory.

#### Success Criteria

Your program should:

- Create a Path object
- Iterate through the directory contents
- Identify directories
- Print only directories

#### Need a Hint?

??? tip "Small Hint"

    Start by listing everything in the directory.

??? tip "Stronger Hint"

    Each item can be checked individually.

??? tip "Almost There"

    Combine:

    ```python
    path.iterdir()
    ```

    with:

    ```python
    item.is_dir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    for item in project.iterdir():
        if item.is_dir():
            print(item)
    ```

#### Why This Exercise Exists

Directory structures often reveal important information about a project.

Examples include:

- Source code organization
- Documentation layouts
- Build artifacts
- Data storage locations

This exercise combines directory traversal and inspection to help learners explore filesystem structures.

---

### Apply

Use the capability in realistic situations.

These exercises reinforce the capability through practical scenarios.

Goal:

👉 Use the capability.

---

### PATHLIB-DO-06

#### Scenario

You are building a reporting script that generates daily reports.

Before the script can save any report files, it needs a place to store them.

The reports should be stored in:

```text
reports
```

#### Objective

Create a program that:

- Creates a Path object for `reports`
- Creates the directory if it does not already exist
- Prints a confirmation message

#### Success Criteria

Your program should:

- Create a Path object
- Create the directory safely
- Avoid raising an error if the directory already exists

#### Need a Hint?

??? tip "Small Hint"

    Your script may be run multiple times.

??? tip "Stronger Hint"

    Directory creation can be configured to ignore existing directories.

??? tip "Almost There"

    Use:

    ```python
    mkdir(exist_ok=True)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    reports = Path("reports")

    reports.mkdir(exist_ok=True)

    print("Reports directory ready")
    ```

#### Why This Exercise Exists

Many programs need to prepare output locations before generating files.

Examples include:

- Report generators
- Log processors
- Export utilities
- Backup tools

Creating directories safely is an important part of building reliable software.

---

### PATHLIB-DO-07

#### Scenario

You are developing a static site generator.

Generated files should be written to:

```text
site/output
```

The directory structure may not exist yet.

Before generating any pages, your program must prepare the output location.

#### Objective

Create a program that creates:

```text
site/output
```

including any required parent directories.

#### Success Criteria

Your program should:

- Create a Path object
- Create all missing parent directories
- Avoid errors if directories already exist

#### Need a Hint?

??? tip "Small Hint"

    More than one directory may need to be created.

??? tip "Stronger Hint"

    pathlib can automatically create parent directories.

??? tip "Almost There"

    Combine:

    ```python
    parents=True
    ```

    and:

    ```python
    exist_ok=True
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    output_dir = Path("site/output")

    output_dir.mkdir(
        parents=True,
        exist_ok=True
    )

    print("Output directory ready")
    ```

#### Why This Exercise Exists

Many development tools generate files inside nested directory structures.

Examples include:

- Static site generators
- Build systems
- Documentation tools
- Data pipelines

Preparing output directories is often one of the first steps in an automation workflow.

---

### PATHLIB-DO-08

#### Scenario

You have cloned a project repository.

Before running development tools, you want to verify that the project contains a directory named:

```text
src
```

#### Objective

Create a program that checks whether:

```text
src
```

exists and prints the result.

#### Success Criteria

Your program should:

- Create a Path object
- Check whether the directory exists
- Print the result

#### Need a Hint?

??? tip "Small Hint"

    Before using a directory, it is often useful to confirm that it exists.

??? tip "Stronger Hint"

    pathlib provides a method specifically for existence checks.

??? tip "Almost There"

    Use:

    ```python
    path.exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    src = Path("src")

    print(src.exists())
    ```

#### Why This Exercise Exists

Many automation scripts need to validate project structures before continuing.

Examples include:

- Build tools
- Deployment scripts
- Repository scanners
- Test runners

Checking for required directories can prevent failures later in a workflow.

---

### PATHLIB-DO-09

#### Scenario

You are exploring an unfamiliar repository.

The project contains several directories such as:

```text
project/
├── src/
├── tests/
├── docs/
├── scripts/
└── tools/
```

You want a quick overview of the available project sections.

#### Objective

Create a program that:

- Lists all items inside the `project` directory
- Prints only the directories

#### Success Criteria

Your program should:

- Create a Path object
- Iterate through directory contents
- Print only directories

#### Need a Hint?

??? tip "Small Hint"

    Begin by listing everything inside the directory.

??? tip "Stronger Hint"

    Each item can be inspected individually.

??? tip "Almost There"

    Combine:

    ```python
    iterdir()
    ```

    with:

    ```python
    is_dir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    for item in project.iterdir():
        if item.is_dir():
            print(item)
    ```

#### Why This Exercise Exists

Directory listings are useful for understanding how projects are organized.

Examples include:

- Source code repositories
- Documentation collections
- Data projects
- Automation systems

Being able to inspect directory structures is a common development task.

---

### PATHLIB-DO-10

#### Scenario

You are building a file archiving tool.

Archived files should be stored inside:

```text
archive
```

Before archiving can begin, your program must ensure the directory exists.

#### Objective

Create a program that:

- Creates an `archive` directory
- Checks whether the directory exists
- Prints the result

#### Success Criteria

Your program should:

- Create a Path object
- Create the directory safely
- Verify its existence
- Print the result

#### Need a Hint?

??? tip "Small Hint"

    This exercise combines creation and verification.

??? tip "Stronger Hint"

    Create the directory first, then perform a check.

??? tip "Almost There"

    Use:

    ```python
    mkdir()
    ```

    and:

    ```python
    exists()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    archive = Path("archive")

    archive.mkdir(exist_ok=True)

    print(archive.exists())
    ```

#### Why This Exercise Exists

Real programs often perform several directory operations as part of a workflow.

Examples include:

- Backup systems
- Archiving tools
- Deployment scripts
- Data processing pipelines

This exercise combines creation and validation, which commonly occur together in production code.

---

## Compose

Combine multiple techniques.

These exercises require bringing together ideas learned earlier in the module.

Goal:

👉 Combine capabilities.

---

### PATHLIB-DO-11

#### Scenario

You are creating a documentation project.

The project should contain the following directory structure:

```text
docs/
├── guides/
├── tutorials/
└── reference/
```

Rather than creating each directory manually, you want Python to prepare the structure for you.

#### Objective

Create a program that creates:

```text
docs/guides
docs/tutorials
docs/reference
```

#### Success Criteria

Your program should:

- Create all required directories
- Create missing parent directories automatically
- Avoid errors if directories already exist

#### Need a Hint?

??? tip "Small Hint"

    Multiple Path objects may be needed.

??? tip "Stronger Hint"

    Create a collection containing the directories you want to create.

??? tip "Almost There"

    Loop through the paths and call:

    ```python
    mkdir(parents=True, exist_ok=True)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    directories = [
        Path("docs/guides"),
        Path("docs/tutorials"),
        Path("docs/reference"),
    ]

    for directory in directories:
        directory.mkdir(
            parents=True,
            exist_ok=True
        )
    ```

#### Why This Exercise Exists

Many projects require a predefined directory structure.

Examples include:

- Documentation sites
- Static site generators
- Software projects
- Data pipelines

This exercise combines directory creation with iteration to automate project setup.

---

### PATHLIB-DO-12

#### Scenario

You are creating a new Python project.

The standard project structure should look like:

```text
my_project/
├── src/
├── tests/
├── docs/
└── scripts/
```

You want Python to create the entire structure automatically.

#### Objective

Create the following directories:

```text
my_project/src
my_project/tests
my_project/docs
my_project/scripts
```

#### Success Criteria

Your program should:

- Create all directories
- Preserve the project hierarchy
- Create parent directories automatically

#### Need a Hint?

??? tip "Small Hint"

    The directories all share a common parent.

??? tip "Stronger Hint"

    Create a base Path and build paths from it.

??? tip "Almost There"

    Use:

    ```python
    project / "src"
    ```

    to build each directory path.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("my_project")

    directories = [
        project / "src",
        project / "tests",
        project / "docs",
        project / "scripts",
    ]

    for directory in directories:
        directory.mkdir(
            parents=True,
            exist_ok=True
        )
    ```

#### Why This Exercise Exists

Developers often create the same project structure repeatedly.

Automatically creating directory layouts saves time and reduces setup mistakes.

This exercise combines path manipulation and directory operations.

---

### PATHLIB-DO-13

#### Scenario

A documentation project should contain:

```text
docs/
├── guides/
├── tutorials/
└── api/
```

You are not sure whether all directories currently exist.

You want Python to identify any missing directories and create them.

#### Objective

Create a program that:

- Checks whether each directory exists
- Creates missing directories
- Prints a message when a directory is created

#### Success Criteria

Your program should:

- Check each directory
- Create missing directories
- Print useful feedback

#### Need a Hint?

??? tip "Small Hint"

    Begin by defining the required directories.

??? tip "Stronger Hint"

    Use an existence check before creating a directory.

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

    directories = [
        Path("docs/guides"),
        Path("docs/tutorials"),
        Path("docs/api"),
    ]

    for directory in directories:
        if not directory.exists():
            directory.mkdir(
                parents=True
            )
            print(f"Created: {directory}")
    ```

#### Why This Exercise Exists

Many automation tools need to verify and repair directory structures.

Examples include:

- Installation scripts
- Project setup tools
- Build systems
- Deployment utilities

This exercise combines inspection and directory creation.

---

### PATHLIB-DO-14

#### Scenario

You are exploring an unfamiliar repository.

Before making changes, you want to see all top-level directories contained within the project.

You are only interested in directories, not files.

#### Objective

Create a program that:

- Lists all items inside a directory named `repository`
- Prints only directories
- Displays the directory name

#### Success Criteria

Your program should:

- Iterate through directory contents
- Identify directories
- Print directory names

#### Need a Hint?

??? tip "Small Hint"

    Start by examining each item inside the directory.

??? tip "Stronger Hint"

    Each item has methods that describe its type.

??? tip "Almost There"

    Combine:

    ```python
    iterdir()
    ```

    with:

    ```python
    is_dir()
    ```

    and:

    ```python
    item.name
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    repository = Path("repository")

    for item in repository.iterdir():
        if item.is_dir():
            print(item.name)
    ```

#### Why This Exercise Exists

Directory exploration is frequently part of automation workflows.

Examples include:

- Repository scanning
- Build tools
- Backup systems
- Project health checks

This exercise combines directory traversal and path inspection.

---

### PATHLIB-DO-15

#### Scenario

You are developing a backup tool.

Before backups can be stored, the following directories must exist:

```text
backup/
├── daily/
├── weekly/
└── monthly/
```

The tool should create any missing directories automatically.

#### Objective

Create a program that:

- Creates the backup directory structure
- Ensures all required directories exist
- Prints the directories that were created

#### Success Criteria

Your program should:

- Create nested directories
- Check for existing directories
- Print helpful status information

#### Need a Hint?

??? tip "Small Hint"

    Create a collection containing all required paths.

??? tip "Stronger Hint"

    Check whether the directory already exists before creating it.

??? tip "Almost There"

    Combine:

    ```python
    exists()
    ```

    and:

    ```python
    mkdir(parents=True)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    directories = [
        Path("backup/daily"),
        Path("backup/weekly"),
        Path("backup/monthly"),
    ]

    for directory in directories:
        if not directory.exists():
            directory.mkdir(
                parents=True
            )
            print(f"Created: {directory}")
    ```

#### Why This Exercise Exists

Real applications often require workspace preparation before performing their primary task.

Examples include:

- Backup utilities
- Data pipelines
- Export tools
- Log processing systems

This exercise combines directory creation, validation, and reporting into a practical workflow.

---

## Automate

Create solutions that reduce repetitive work.

These exercises focus on building practical automations.

Goal:

👉 Automate solutions.

---

### PATHLIB-DO-16

#### Scenario

You frequently start small Python projects.

Every project should contain the following structure:

```text
project/
├── src/
├── tests/
├── docs/
└── data/
```

Rather than creating these directories manually each time, you decide to automate the setup process.

#### Objective

Create a program that:

- Creates the project directory structure
- Creates any missing directories
- Prints the directories that were created

#### Success Criteria

Your program should:

- Create all required directories
- Create parent directories automatically
- Print useful status information

#### Need a Hint?

??? tip "Small Hint"

    Start by defining all required directory paths.

??? tip "Stronger Hint"

    Store the paths in a collection and process them in a loop.

??? tip "Almost There"

    Use:

    ```python
    mkdir(parents=True, exist_ok=True)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    project = Path("project")

    directories = [
        project / "src",
        project / "tests",
        project / "docs",
        project / "data",
    ]

    for directory in directories:
        directory.mkdir(
            parents=True,
            exist_ok=True,
        )
        print(f"Ready: {directory}")
    ```

#### Why This Exercise Exists

Developers often create the same directory structures repeatedly.

Examples include:

- Python projects
- Documentation projects
- Data pipelines
- Automation tools

Automating project setup saves time and ensures consistency.

---

### PATHLIB-DO-17

#### Scenario

You are building a static site generator.

Before pages can be generated, the following output structure must exist:

```text
site/
├── pages/
├── assets/
├── images/
└── css/
```

You want Python to prepare the workspace automatically.

#### Objective

Create a program that:

- Creates the required output directories
- Creates parent directories when needed
- Prints the created directory structure

#### Success Criteria

Your program should:

- Create all required directories
- Create missing parent directories
- Print each prepared directory

#### Need a Hint?

??? tip "Small Hint"

    This is similar to setting up a project structure.

??? tip "Stronger Hint"

    Build each directory path from a common parent directory.

??? tip "Almost There"

    Use:

    ```python
    site / "pages"
    ```

    and similar paths for the remaining directories.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    site = Path("site")

    directories = [
        site / "pages",
        site / "assets",
        site / "images",
        site / "css",
    ]

    for directory in directories:
        directory.mkdir(
            parents=True,
            exist_ok=True,
        )
        print(f"Ready: {directory}")
    ```

#### Why This Exercise Exists

Many tools require a directory structure before any work can begin.

Examples include:

- Static site generators
- Build systems
- Documentation tools
- Asset pipelines

Preparing workspaces is a common automation task.

---

### PATHLIB-DO-18

#### Scenario

You are creating a backup utility.

The tool stores backups using the following structure:

```text
backups/
├── daily/
├── weekly/
├── monthly/
└── yearly/
```

Every time the utility runs, it should ensure the directories exist.

#### Objective

Create a program that:

- Creates any missing backup directories
- Verifies that each directory exists
- Prints a summary of the backup structure

#### Success Criteria

Your program should:

- Create required directories
- Check existence
- Print directory information

#### Need a Hint?

??? tip "Small Hint"

    You will need both directory creation and directory inspection.

??? tip "Stronger Hint"

    Create the directories first, then verify them.

??? tip "Almost There"

    Use:

    ```python
    exists()
    ```

    after:

    ```python
    mkdir()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    directories = [
        Path("backups/daily"),
        Path("backups/weekly"),
        Path("backups/monthly"),
        Path("backups/yearly"),
    ]

    for directory in directories:
        directory.mkdir(
            parents=True,
            exist_ok=True,
        )

        print(
            f"{directory}: {directory.exists()}"
        )
    ```

#### Why This Exercise Exists

Reliable automation often begins with ensuring required resources exist.

Examples include:

- Backup systems
- Archive systems
- Scheduled jobs
- Data processing pipelines

This exercise combines creation, validation, and reporting.

---

### PATHLIB-DO-19

#### Scenario

You are investigating a repository and would like a quick overview of its top-level directory structure.

Rather than opening folders manually, you decide to generate a simple report.

#### Objective

Create a program that:

- Examines the `repository` directory
- Finds all immediate subdirectories
- Prints the name of each directory
- Displays the total number of directories found

#### Success Criteria

Your program should:

- Iterate through directory contents
- Identify directories
- Count directories
- Print a summary report

#### Need a Hint?

??? tip "Small Hint"

    You have already learned how to list directories.

??? tip "Stronger Hint"

    Store matching directories before printing them.

??? tip "Almost There"

    Consider:

    ```python
    directories = [
        item
        for item in repository.iterdir()
        if item.is_dir()
    ]
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    repository = Path("repository")

    directories = [
        item
        for item in repository.iterdir()
        if item.is_dir()
    ]

    for directory in directories:
        print(directory.name)

    print(
        f"\nTotal directories: {len(directories)}"
    )
    ```

#### Why This Exercise Exists

Many developer tools begin by exploring a project's structure.

Examples include:

- Repository scanners
- Build tools
- Documentation generators
- Project analyzers

This exercise demonstrates how directory operations can support reporting and analysis.

---

### PATHLIB-DO-20

#### Scenario

You are creating a workspace bootstrapper for data analysis projects.

Every new project should contain:

```text
workspace/
├── raw-data/
├── processed-data/
├── reports/
├── notebooks/
└── exports/
```

The tool should create the structure and provide a summary when finished.

#### Objective

Create a program that:

- Creates the complete workspace structure
- Creates parent directories as needed
- Prints each created directory
- Prints the total number of directories prepared

#### Success Criteria

Your program should:

- Create the entire workspace structure
- Handle missing parent directories
- Produce a useful summary report

#### Need a Hint?

??? tip "Small Hint"

    Define the required directory paths first.

??? tip "Stronger Hint"

    Store the paths in a collection and loop through them.

??? tip "Almost There"

    Use:

    ```python
    len(directories)
    ```

    to generate the final summary.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    workspace = Path("workspace")

    directories = [
        workspace / "raw-data",
        workspace / "processed-data",
        workspace / "reports",
        workspace / "notebooks",
        workspace / "exports",
    ]

    for directory in directories:
        directory.mkdir(
            parents=True,
            exist_ok=True,
        )
        print(f"Ready: {directory}")

    print(
        f"\nPrepared {len(directories)} directories."
    )
    ```

#### Why This Exercise Exists

Many real-world automation tools begin by preparing a structured workspace.

Examples include:

- Data analysis projects
- ETL pipelines
- Reporting systems
- Machine learning projects

This exercise brings together the core directory operations learned throughout the capability:

- Creating directories
- Creating nested directories
- Checking existence
- Organizing directory structures
- Generating summary information

It is the closest exercise in this capability to a real utility that a developer might use regularly.