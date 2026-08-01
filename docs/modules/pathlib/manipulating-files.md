# pathlib - Manipulating Paths

## Overview

Finding and reading files is useful, but many real-world programs also need to modify paths.

Common tasks include:

- Changing file extensions
- Generating backup filenames
- Moving from one directory to another
- Constructing related file paths
- Creating output paths for generated files

Path manipulation allows you to work with filesystem locations without manually building strings.

Using pathlib makes path manipulation safer, clearer, and more portable across operating systems.

---

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

### PATHLIB-MP-01

#### Scenario

You are building a script that processes a file located at:

```text
notes/todo.txt
```

Before working with the file, you would like to display its name to the user.

#### Objective

Create a `Path` object representing:

```text
notes/todo.txt
```

Print only the file name.

#### Success Criteria

Your program should:

- Create a Path object
- Extract the file name
- Print the file name

#### Need a Hint?

??? tip "Small Hint"

    Path objects provide information about different parts of a path.

??? tip "Stronger Hint"

    You do not need to split strings manually.

??? tip "Almost There"

    Use:

    ```python
    path.name
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/todo.txt")

    print(path.name)
    ```

#### Why This Exercise Exists

Developers frequently need information about a file after locating it.

Examples include:

- Displaying filenames to users
- Generating reports
- Logging operations

Pathlib makes it easy to extract this information without manually manipulating strings.

---

### PATHLIB-MP-02

#### Scenario

You are writing a script that processes uploaded files.

Before deciding how to handle a file, you need to determine its type.

The file is located at:

```text
uploads/report.pdf
```

#### Objective

Create a `Path` object representing:

```text
uploads/report.pdf
```

Print the file extension.

#### Success Criteria

Your program should:

- Create a Path object
- Extract the file extension
- Print the extension

#### Need a Hint?

??? tip "Small Hint"

    Path objects expose useful pieces of information about files.

??? tip "Stronger Hint"

    The extension includes the leading dot.

??? tip "Almost There"

    Use:

    ```python
    path.suffix
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("uploads/report.pdf")

    print(path.suffix)
    ```

#### Why This Exercise Exists

File extensions are often used to determine how files should be processed.

Examples include:

- Images
- PDFs
- Text files
- Configuration files

This capability helps programs make decisions based on file type.

---

### PATHLIB-MP-03

#### Scenario

You have generated a report and want to save it in a different format.

The original file path is:

```text
reports/monthly.txt
```

You would like to create a path for:

```text
reports/monthly.md
```

without manually building a string.

#### Objective

Create a `Path` object representing:

```text
reports/monthly.txt
```

Create a new path with a `.md` extension and print it.

#### Success Criteria

Your program should:

- Create a Path object
- Replace the file extension
- Print the new path

#### Need a Hint?

??? tip "Small Hint"

    Pathlib can create a new path based on an existing one.

??? tip "Stronger Hint"

    You do not need to remove the old extension yourself.

??? tip "Almost There"

    Use:

    ```python
    path.with_suffix(".md")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("reports/monthly.txt")

    markdown_path = path.with_suffix(".md")

    print(markdown_path)
    ```

#### Why This Exercise Exists

Programs often generate alternative versions of files.

Examples include:

- Converting CSV files to JSON
- Exporting reports
- Generating HTML from Markdown

Changing file extensions is a common path manipulation task.

---

### PATHLIB-MP-04

#### Scenario

You have discovered a file at:

```text
projects/python/README.md
```

Before processing the file, you would like to determine which directory contains it.

#### Objective

Create a `Path` object representing:

```text
projects/python/README.md
```

Print the path's parent directory.

#### Success Criteria

Your program should:

- Create a Path object
- Access the parent directory
- Print the parent path

#### Need a Hint?

??? tip "Small Hint"

    A path contains both a file name and a directory location.

??? tip "Stronger Hint"

    Pathlib provides a way to move one level up.

??? tip "Almost There"

    Use:

    ```python
    path.parent
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("projects/python/README.md")

    print(path.parent)
    ```

#### Why This Exercise Exists

Many filesystem tasks require moving between files and directories.

Examples include:

- Creating related files
- Building reports
- Generating output locations

Understanding parent directories is a fundamental path manipulation skill.

---

### PATHLIB-MP-05

#### Scenario

You maintain project documentation inside:

```text
docs
```

You need a path representing:

```text
docs/guide.md
```

Instead of manually concatenating strings, you want pathlib to construct the path.

#### Objective

Create a `Path` object representing:

```text
docs
```

Create a new path representing:

```text
docs/guide.md
```

Print the resulting path.

#### Success Criteria

Your program should:

- Create a Path object for `docs`
- Create a path inside that directory
- Print the resulting path

#### Need a Hint?

??? tip "Small Hint"

    Path objects can be combined to create new paths.

??? tip "Stronger Hint"

    There is an operator designed specifically for building paths.

??? tip "Almost There"

    Use:

    ```python
    directory / "guide.md"
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    docs = Path("docs")

    guide = docs / "guide.md"

    print(guide)
    ```

#### Why This Exercise Exists

Constructing paths is one of the most common filesystem operations.

Examples include:

- Creating output files
- Generating reports
- Writing processed data
- Building directory structures

Using pathlib's path-building features is safer and more readable than manually combining strings.

---

### Apply

Use the capability in realistic situations.

These exercises reinforce the capability through practical scenarios.

Goal:

👉 Use the capability.

---

### PATHLIB-MP-06

#### Scenario

You are building a script that creates backups before modifying important files.

The original file is located at:

```text
notes/todo.txt
```

Before making any changes, you want to generate a backup file named:

```text
notes/todo.backup.txt
```

#### Objective

Create a `Path` object representing:

```text
notes/todo.txt
```

Create a new path representing:

```text
notes/todo.backup.txt
```

Print the backup path.

#### Success Criteria

Your program should:

- Create a Path object
- Generate a backup filename
- Preserve the original directory
- Print the resulting path

#### Need a Hint?

??? tip "Small Hint"

    You can use information from the original filename to create a new filename.

??? tip "Stronger Hint"

    The file name and extension can be accessed separately.

??? tip "Almost There"

    Use:

    ```python
    path.stem
    path.suffix
    ```

    to build a new filename.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/todo.txt")

    backup = path.with_name(
        f"{path.stem}.backup{path.suffix}"
    )

    print(backup)
    ```

#### Why This Exercise Exists

Backup files are commonly created before modifying existing files.

Examples include:

- Configuration files
- Reports
- Documentation
- Source code

This exercise demonstrates how path manipulation can generate related file paths without manually constructing strings.

---

### PATHLIB-MP-07

#### Scenario

You have a Markdown document located at:

```text
posts/python-tips.md
```

A static site generator will eventually create an HTML version of the file.

You want to determine what the HTML output path should be.

#### Objective

Create a `Path` object representing:

```text
posts/python-tips.md
```

Create a new path representing:

```text
posts/python-tips.html
```

Print the new path.

#### Success Criteria

Your program should:

- Create a Path object
- Change the file extension
- Print the resulting path

#### Need a Hint?

??? tip "Small Hint"

    You do not need to rebuild the entire path.

??? tip "Stronger Hint"

    pathlib can create a new path with a different suffix.

??? tip "Almost There"

    Use:

    ```python
    path.with_suffix(".html")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    markdown_file = Path("posts/python-tips.md")

    html_file = markdown_file.with_suffix(".html")

    print(html_file)
    ```

#### Why This Exercise Exists

Many automation tools generate alternative versions of existing files.

Examples include:

- Markdown to HTML
- CSV to JSON
- Images to thumbnails
- Reports to PDFs

Being able to easily generate related file paths is a valuable skill.

---

### PATHLIB-MP-08

#### Scenario

A reporting system stores generated reports inside the directory:

```text
reports
```

Today's report should be saved as:

```text
reports/sales-report.txt
```

You want pathlib to construct the full path.

#### Objective

Create a `Path` object representing:

```text
reports
```

Create a new path for:

```text
sales-report.txt
```

inside that directory.

Print the resulting path.

#### Success Criteria

Your program should:

- Create a Path object for the directory
- Generate a file path inside the directory
- Print the resulting path

#### Need a Hint?

??? tip "Small Hint"

    Directories and filenames can be combined.

??? tip "Stronger Hint"

    pathlib provides a dedicated operator for path construction.

??? tip "Almost There"

    Use:

    ```python
    reports / "sales-report.txt"
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    reports = Path("reports")

    report_file = reports / "sales-report.txt"

    print(report_file)
    ```

#### Why This Exercise Exists

Programs frequently generate files inside specific directories.

Examples include:

- Reports
- Logs
- Exports
- Configuration files

Constructing paths with pathlib is more reliable than manual string concatenation.

---

### PATHLIB-MP-09

#### Scenario

You have a file located at:

```text
projects/python/README.md
```

You want to create an archive directory next to the file:

```text
projects/python/archive
```

#### Objective

Create a `Path` object representing:

```text
projects/python/README.md
```

Create a new path representing:

```text
projects/python/archive
```

Print the new path.

#### Success Criteria

Your program should:

- Create a Path object
- Access the parent directory
- Create a new path inside that directory
- Print the resulting path

#### Need a Hint?

??? tip "Small Hint"

    Start by finding the directory containing the file.

??? tip "Stronger Hint"

    Once you have the parent directory, create a new path inside it.

??? tip "Almost There"

    Use:

    ```python
    path.parent / "archive"
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("projects/python/README.md")

    archive = path.parent / "archive"

    print(archive)
    ```

#### Why This Exercise Exists

Many automation tasks generate related directories based on existing file locations.

Examples include:

- Backup folders
- Archive folders
- Export directories
- Build outputs

This exercise combines multiple path manipulation techniques.

---

### PATHLIB-MP-10

#### Scenario

You maintain a directory of raw data files.

One file is located at:

```text
data/customers.csv
```

You want to create a path for a processed version of the file:

```text
data/customers.json
```

#### Objective

Create a `Path` object representing:

```text
data/customers.csv
```

Create and print a path representing:

```text
data/customers.json
```

#### Success Criteria

Your program should:

- Create a Path object
- Replace the file extension
- Print the new path

#### Need a Hint?

??? tip "Small Hint"

    The filename should remain the same.

??? tip "Stronger Hint"

    Only the extension needs to change.

??? tip "Almost There"

    Use:

    ```python
    path.with_suffix(".json")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("data/customers.csv")

    output_path = path.with_suffix(".json")

    print(output_path)
    ```

#### Why This Exercise Exists

Data processing workflows frequently generate new files from existing ones.

Examples include:

- CSV to JSON conversion
- Markdown to HTML generation
- Log exports
- Report generation

This exercise reinforces the idea that paths can be transformed just like data.

---

### Compose

Combine multiple techniques.

These exercises require bringing together ideas learned earlier in the module.

Goal:

👉 Combine capabilities.

---

### PATHLIB-MP-11

#### Scenario

You are building a static site generator.

Markdown files are stored in:

```text
content/
├── guide.md
├── tips.md
└── tutorial.md
```

Each Markdown file should eventually become an HTML file.

Before generating content, you need to determine what the output paths should be.

#### Objective

Create a `Path` object representing:

```text
content/guide.md
```

Create a new path representing:

```text
content/guide.html
```

Print:

- The original path
- The new output path

#### Success Criteria

Your program should:

- Create a Path object
- Replace the file extension
- Print both paths

#### Need a Hint?

??? tip "Small Hint"

    The directory should remain unchanged.

??? tip "Stronger Hint"

    Only the file extension needs to change.

??? tip "Almost There"

    Use:

    ```python
    path.with_suffix(".html")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    source = Path("content/guide.md")
    output = source.with_suffix(".html")

    print(source)
    print(output)
    ```

#### Why This Exercise Exists

Many automation tools generate output files from source files.

Examples include:

- Markdown to HTML conversion
- CSV to JSON conversion
- Template rendering
- Report generation

This exercise combines file inspection and path transformation into a practical workflow.

---

### PATHLIB-MP-12

#### Scenario

You are creating a photo management tool.

An image is stored at:

```text
photos/vacation.jpg
```

For every image, the tool should create a thumbnail file named:

```text
photos/vacation_thumb.jpg
```

Before generating the image, you need to determine the thumbnail path.

#### Objective

Create a `Path` object representing:

```text
photos/vacation.jpg
```

Create a new path representing:

```text
photos/vacation_thumb.jpg
```

Print the thumbnail path.

#### Success Criteria

Your program should:

- Create a Path object
- Use the original filename
- Generate a new filename
- Preserve the original extension

#### Need a Hint?

??? tip "Small Hint"

    You will need both the filename and extension.

??? tip "Stronger Hint"

    The filename without the extension can be accessed separately.

??? tip "Almost There"

    Use:

    ```python
    path.stem
    path.suffix
    path.with_name(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    image = Path("photos/vacation.jpg")

    thumbnail = image.with_name(
        f"{image.stem}_thumb{image.suffix}"
    )

    print(thumbnail)
    ```

#### Why This Exercise Exists

Automation tools frequently generate related files.

Examples include:

- Thumbnails
- Backups
- Processed data
- Exported reports

This exercise combines several path manipulation techniques to generate a new filename.

---

### PATHLIB-MP-13

#### Scenario

You are writing a documentation publishing tool.

A document exists at:

```text
docs/getting-started.md
```

Published files should be stored in:

```text
site/getting-started.html
```

Before creating the output file, you need to generate the destination path.

#### Objective

Create a `Path` object representing:

```text
docs/getting-started.md
```

Create a new path representing:

```text
site/getting-started.html
```

Print the new path.

#### Success Criteria

Your program should:

- Create a Path object
- Extract the filename
- Change the extension
- Place the file inside the `site` directory

#### Need a Hint?

??? tip "Small Hint"

    Start by retrieving the filename.

??? tip "Stronger Hint"

    You can create a new path in a different directory.

??? tip "Almost There"

    Use:

    ```python
    path.with_suffix(".html")
    ```

    and combine it with:

    ```python
    Path("site")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    source = Path("docs/getting-started.md")

    output = Path("site") / source.with_suffix(".html").name

    print(output)
    ```

#### Why This Exercise Exists

Many real-world tools transform files while changing their destination.

Examples include:

- Static site generators
- Documentation builders
- Report exporters
- Data processing pipelines

This exercise demonstrates how pathlib can generate output locations programmatically.

---

### PATHLIB-MP-14

#### Scenario

You are building a backup utility.

A file exists at:

```text
projects/python/config.json
```

Backups should be stored inside a sibling directory:

```text
projects/python/backups/config.json
```

Before copying the file, you need to determine where the backup should be stored.

#### Objective

Create a `Path` object representing:

```text
projects/python/config.json
```

Create a path representing:

```text
projects/python/backups/config.json
```

Print the backup path.

#### Success Criteria

Your program should:

- Create a Path object
- Access the parent directory
- Create a backups directory path
- Preserve the original filename

#### Need a Hint?

??? tip "Small Hint"

    Start with the file's parent directory.

??? tip "Stronger Hint"

    Build the backups path one step at a time.

??? tip "Almost There"

    Use:

    ```python
    path.parent
    path.name
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("projects/python/config.json")

    backup_path = (
        path.parent
        / "backups"
        / path.name
    )

    print(backup_path)
    ```

#### Why This Exercise Exists

Path manipulation often involves generating related directory structures.

Examples include:

- Backup systems
- Archive tools
- Export systems
- Build pipelines

This exercise combines several previously learned path manipulation techniques.

---

### PATHLIB-MP-15

#### Scenario

You are creating a data processing pipeline.

The source file is:

```text
data/sales.csv
```

The pipeline produces:

```text
exports/sales.json
```

Before processing the data, you need to determine the output path.

#### Objective

Create a `Path` object representing:

```text
data/sales.csv
```

Create a path representing:

```text
exports/sales.json
```

Print the resulting path.

#### Success Criteria

Your program should:

- Create a Path object
- Keep the original filename
- Change the extension
- Move the file into the `exports` directory

#### Need a Hint?

??? tip "Small Hint"

    You can reuse information from the original path.

??? tip "Stronger Hint"

    The filename and extension can be manipulated independently.

??? tip "Almost There"

    Create a new filename and place it inside:

    ```python
    Path("exports")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    source = Path("data/sales.csv")

    output = Path("exports") / source.with_suffix(".json").name

    print(output)
    ```

#### Why This Exercise Exists

Many automation workflows transform both a file's format and location.

Examples include:

- Data conversion pipelines
- Export tools
- Build systems
- Deployment workflows

This exercise reinforces how multiple path manipulation operations can be combined to generate useful output paths.

---

### Automate

Create solutions that reduce repetitive work.

These exercises focus on building practical automations.

Goal:

👉 Automate solutions.

---

### PATHLIB-MP-16

#### Scenario

You are creating a backup utility.

The utility scans a directory and creates backup filenames for every text file it finds.

Examples:

```text
notes/todo.txt
```

becomes:

```text
notes/todo.backup.txt
```

Before creating the backups, you need a program that generates the backup paths automatically.

#### Objective

Create a program that:

- Searches a directory named `notes`
- Finds all `.txt` files
- Generates a backup path for each file
- Prints both the original path and backup path

#### Success Criteria

Your program should:

- Find all text files
- Create a backup path for each file
- Preserve the original directory
- Print both paths

#### Need a Hint?

??? tip "Small Hint"

    You will need both file discovery and path manipulation.

??? tip "Stronger Hint"

    Each discovered file is a Path object that can be transformed into a backup path.

??? tip "Almost There"

    Use:

    ```python
    path.stem
    path.suffix
    path.with_name(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = Path("notes")

    for file in notes.rglob("*.txt"):
        backup = file.with*name(
            f"{file.stem}.ba*kup{file.suffix}"
        )

     *  print(f"Original: {file}")
     *  print(f"Backup:   {backup}")
   *    print()
    ```

#### Why This *xercise Exists

Many automation to*ls generate related files from exi*ting files.

Examples include:

- *ackups
- Temporary files
- Export *iles
- Generated reports

This exe*cise combines file discovery and p*th manipulation to automate a real*stic development task.

---

### PA*HLIB-MP-17

#### Scenario

You are *uilding a static site generator.

*arkdown files are stored throughou*:

```text
content/
```

For each *arkdown file, you need to determin* the HTML file that should be gene*ated.

Examples:

```text
content/*uide.md
```

becomes:

```text
con*ent/guide.html
```

#### Objective
*Create a program that:

- Finds al* Markdown files inside `content`
-*Generates the corresponding HTML p*th
- Prints the source file and ou*put file

#### Success Criteria

Yo*r program should:

- Search recursively for Markdown files
- Create corresponding HTML paths
- Print both source and destination paths

#### Need a Hint?

??? tip "Small Hint"

    The output path is based on the original file.

??? tip "Stronger Hint"

    Only the file extension changes.

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
        output = file.with_suffix(".html")

        print(f"Source: {file}")
        print(f"Output: {output}")
        print()
    ```

#### Why This Exercise Exists

Many real-world tools transform one type of file into another.

Examples include:

- Static site generators
- Documentation tools
- Asset pipelines
- Report exporters

This exercise demonstrates how path manipulation helps automate those workflows.

---

### PATHLIB-MP-18

#### Scenario

You are creating an image processing tool.

Images are stored throughout:

```text
photos/
```

For each image, the tool will eventually create a thumbnail.

Before generating the thumbnails, you want to determine all thumbnail paths.

Example:

```text
photos/vacation.jpg
```

becomes:

```text
photos/vacation_thumb.jpg
```

#### Objective

Create a program that:

- Finds all `.jpg` files
- Creates a thumbnail path for each file
- Prints the original path and thumbnail path

#### Success Criteria

Your program should:

- Search recursively for image files
- Generate thumbnail filenames
- Preserve the original directory and extension
- Print both paths

#### Need a Hint?

??? tip "Small Hint"

    You'll need to modify the filename while keeping the extension.

??? tip "Stronger Hint"

    Use the filename stem and suffix separately.

??? tip "Almost There"

    Combine:

    ```python
    file.stem
    file.suffix
    file.with_name(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    photos = Path("photos")

    for file in photos.rglob("*.jpg"):
        thumbnail = file.with_name(
            f"{file.stem}_thumb{file.suffix}"
        )

        print(f"Image:     {file}")
        print(f"Thumbnail: {thumbnail}")
        print()
    ```

#### Why This Exercise Exists

Image processing pipelines frequently create related files.

Examples include:

- Thumbnails
- Compressed versions
- Watermarked copies
- Resized exports

This exercise reinforces automated path generation for large collections of files.

---

### PATHLIB-MP-19

#### Scenario

You are creating a documentation publishing tool.

Source files are located in:

```text
docs/
```

Published files should be stored in:

```text
site/
```

Every Markdown file should become an HTML file in the output directory.

Example:

```text
docs/tutorial.md
```

becomes:

```text
site/tutorial.html
```

#### Objective

Create a program that:

- Finds all Markdown files in `docs`
- Generates corresponding HTML files in `site`
- Prints the source and destination paths

#### Success Criteria

Your program should:

- Search recursively for Markdown files
- Change the file extension
- Change the destination directory
- Print both paths

#### Need a Hint?

??? tip "Small Hint"

    The output path uses information from the source file.

??? tip "Stronger Hint"

    The filename remains the same, but the extension and directory change.

??? tip "Almost There"

    Build the new path using:

    ```python
    Path("site")
    ```

    and:

    ```python
    file.with_suffix(".html").name
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    docs = Path("docs")

    for file in docs.rglob("*.md"):
        output = Path("site") / file.with_suffix(".html").name

        print(f"Source: {file}")
        print(f"Output: {output}")
        print()
    ```

#### Why This Exercise Exists

Many automation tools separate source files from generated output.

Examples include:

- Documentation systems
- Static site generators
- Build systems
- Deployment workflows

This exercise combines multiple path transformations into a practical automation scenario.

---

### PATHLIB-MP-20

#### Scenario

You are building a repository analysis tool.

The tool scans a repository and determines where generated reports should be stored.

For every Python file discovered:

```text
src/api/main.py
```

the tool should generate:

```text
reports/main-report.txt
```

Before creating reports, you need a program that calculates all output paths.

#### Objective

Create a program that:

- Finds every Python file in `src`
- Creates a report filename based on each Python file
- Stores reports inside a `reports` directory
- Prints the source file and report path

#### Success Criteria

Your program should:

- Search recursively for Python files
- Generate report filenames
- Change both filename and directory
- Print both paths

#### Need a Hint?

??? tip "Small Hint"

    You need information from the original file name.

??? tip "Stronger Hint"

    Create a new filename using the original stem.

??? tip "Almost There"

    Use:

    ```python
    file.stem
    ```

    to build:

    ```text
    main-report.txt
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    src = Path("src")

    for file in src.rglob("*.py"):
        report = (
            Path("reports")
            / f"{file.stem}-report.txt"
        )

        print(f"Source: {file}")
        print(f"Report: {report}")
        print()
    ```

#### Why This Exercise Exists

Many developer tools generate new files based on files they discover.

Examples include:

- Repository scanners
- Documentation generators
- Test runners
- Static analysis tools

This exercise brings together file discovery, path inspection, filename generation, and path construction in a workflow that resembles a real software tool.