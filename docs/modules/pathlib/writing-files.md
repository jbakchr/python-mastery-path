# pathlib - Writing Files

## **Overview**

🚧 Section Needs Elaboration (See creating-files.md for example)

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

🚧 Section Needs Elaboration (See creating-files.md for example)

---

## **Discover**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

### PATHLIB-WF-01

#### Scenario

You want to save a simple note for later.

The note should be stored in:

```
notes/todo.txt
```

with the text:

```
Buy milk
```

#### Objective

Create a Path object representing:

```
notes/todo.txt
```

Write:

```
Buy milk
```

to the file.

#### Success Criteria

Your program should:

- Create a Path object
- Write text to the file
- Create the file if it does not already exist

#### Need a Hint?

??? tip "Small Hint"

    pathlib can write text directly to a file.

??? tip "Stronger Hint"

    Look for a method that saves a string to a file.

??? tip "Almost There"

    Use:

    ```python
    path.write_text("Buy milk")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/todo.txt")

    path.write_text("Buy milk")
    ```

#### Why This Exercise Exists

Saving information to a file is one of the most common filesystem tasks.

Many programs generate text that needs to be stored for later use.

---

### PATHLIB-WF-02

#### Scenario

You are keeping a personal journal.

Today's entry should be saved in:

```
journal/today.txt
```

with the text:

```
Today I learned how to write files using pathlib.
```

#### Objective

Create a Path object and write the journal entry to the file.

#### Success Criteria

Your program should:

- Create a Path object
- Write the journal entry
- Save the text to the file

#### Need a Hint?

??? tip "Small Hint"

    The text should be provided as a string.

??? tip "Stronger Hint"

    Use `write_text()` to store text in a file.

??? tip "Almost There"

    Use:

    ```python
    path.write_text(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("journal/today.txt")

    path.write_text(
        "Today I learned how to write files using pathlib."
    )
    ```

#### Why This Exercise Exists

Many applications need to save user-generated content.

Examples include:

- Notes
- Journal entries
- Comments
- Documentation

---

### PATHLIB-WF-03

#### Scenario

You are creating a configuration file for a new application.

The file should be:

```
config.txt
```

and contain:

```
debug=true
```

#### Objective

Create a Path object and write the configuration setting to the file.

#### Success Criteria

Your program should:

- Create a Path object
- Write the configuration setting
- Save the file

#### Need a Hint?

??? tip "Small Hint"

    Configuration files are often simple text files.

??? tip "Stronger Hint"

    The text being saved is:

    ```text
    debug=true
    ```

??? tip "Almost There"

    Use:

    ```python
    path.write_text("debug=true")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("config.txt")

    path.write_text("debug=true")
    ```

#### Why This Exercise Exists

Many applications read and write configuration files.

Writing simple text files is often the first step toward creating more advanced automation tools.

---

### PATHLIB-WF-04

#### Scenario

You are generating a project report.

The report should be saved as:

```
report.txt
```

The report should contain:

```
Project Status: Complete
```

#### Objective

Create a Path object and save the report text to the file.

#### Success Criteria

Your program should:

- Create a Path object
- Write the report text
- Save the file

#### Need a Hint?

??? tip "Small Hint"

    Reports are often generated automatically and saved to files.

??? tip "Stronger Hint"

    Store the report text as a string.

??? tip "Almost There"

    Use:

    ```python
    path.write_text("Project Status: Complete")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("report.txt")

    path.write_text("Project Status: Complete")
    ```

#### Why This Exercise Exists

Many automation tasks produce output that should be saved.

Reports are one of the most common forms of generated output.

---

### PATHLIB-WF-05

#### Scenario

You are building a simple text generation tool.

The generated message is:

```
Hello, Python Mastery Path!
```

The message should be saved to:

```
output.txt
```

#### Objective

Store the message in a variable named `message`.

Write the message to the file.

#### Success Criteria

Your program should:

- Create a variable named `message`
- Create a Path object
- Write the variable contents to the file

#### Need a Hint?

??? tip "Small Hint"

    The text does not need to be written directly.

??? tip "Stronger Hint"

    Store the text in a variable first.

??? tip "Almost There"

    Use:

    ```python
    path.write_text(message)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    message = "Hello, Python Mastery Path!"

    path = Path("output.txt")

    path.write_text(message)
    ```

#### Why This Exercise Exists

Programs rarely write hardcoded text directly to files.

More commonly, they generate or collect information and then save that information for later use.

This exercise introduces the idea that variables and generated content can be written to files.

---

## **Apply**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

### PATHLIB-WF-06

#### Scenario

You have finished a meeting and want to save your notes.

The notes should be stored in:

```
meeting-notes.txt
```

with the content:

```text
Project kickoff completed.
Next meeting scheduled for Friday.
```

#### Objective

Create a Path object and save the meeting notes to the file.

#### Success Criteria

Your program should:

- Create a Path object
- Write the meeting notes
- Save the file

#### Need a Hint?

??? tip "Small Hint"

    Meeting notes are simply text that can be written to a file.

??? tip "Stronger Hint"

    Store the notes in a variable before writing them.

??? tip "Almost There"

    Use:

    ```python
    path.write_text(notes)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    notes = """Project kickoff completed.
    Next meeting scheduled for Friday."""

    path = Path("meeting-notes.txt")

    path.write_text(notes)
    ```

#### Why This Exercise Exists

Developers and teams frequently save notes, meeting summaries, and planning information as text files.

Writing files provides a simple way to preserve information for later use.

---

### PATHLIB-WF-07

#### Scenario

You are building a simple todo application.

The application should save a list of tasks to:

```
todos.txt
```

#### Objective

Write the following tasks to the file:

```text
Buy groceries
Review project plan
Schedule team meeting
```

#### Success Criteria

Your program should:

- Create a Path object
- Save all tasks to the file
- Write each task on its own line

#### Need a Hint?

??? tip "Small Hint"

    Text files can contain multiple lines.

??? tip "Stronger Hint"

    Use a multiline string.

??? tip "Almost There"

    Write the entire string using:

    ```python
    path.write_text(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    tasks = """Buy groceries
    Review project plan
    Schedule team meeting"""

    path = Path("todos.txt")

    path.write_text(tasks)
    ```

#### Why This Exercise Exists

Many applications store collections of information as simple text files.

Todo lists are a common real-world example.

---

### PATHLIB-WF-08

#### Scenario

You are generating a project status report.

The report should be stored in:

```
status-report.txt
```

The report content should include:

```text
Project: Python Mastery Path
Status: In Progress
```

#### Objective

Save the report to a file.

#### Success Criteria

Your program should:

- Create a Path object
- Create the report text
- Save the report

#### Need a Hint?

??? tip "Small Hint"

    Build the report as a string first.

??? tip "Stronger Hint"

    Store the report text in a variable.

??? tip "Almost There"

    Use:

    ```python
    path.write_text(report)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    report = """Project: Python Mastery Path
    Status: In Progress"""

    path = Path("status-report.txt")

    path.write_text(report)
    ```

#### Why This Exercise Exists

Many automation scripts generate reports that need to be saved for later review.

This is a common use case for writing files.

---

### PATHLIB-WF-09

#### Scenario

Your application allows users to configure settings.

The application should save:

```text
theme=dark
language=en
```

to:

```
settings.txt
```

#### Objective

Create a configuration file containing the settings.

#### Success Criteria

Your program should:

- Create a Path object
- Write the settings
- Save the file

#### Need a Hint?

??? tip "Small Hint"

    Configuration files often contain simple key=value pairs.

??? tip "Stronger Hint"

    Create a multiline string containing the settings.

??? tip "Almost There"

    Use:

    ```python
    path.write_text(settings)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    settings = """theme=dark
    language=en"""

    path = Path("settings.txt")

    path.write_text(settings)
    ```

#### Why This Exercise Exists

Many applications store settings and preferences in text files.

Writing configuration files is a practical and common task.

---

### PATHLIB-WF-10

#### Scenario

You are creating a simple quote generator.

A quote is stored in a variable and should be saved to:

```
quote.txt
```

#### Objective

Create a variable named `quote`.

Store any motivational quote inside it.

Write the quote to a file.

#### Success Criteria

Your program should:

- Create a variable named `quote`
- Create a Path object
- Write the quote to the file

#### Need a Hint?

??? tip "Small Hint"

    The file contents can come from a variable.

??? tip "Stronger Hint"

    Store the quote in a string variable first.

??? tip "Almost There"

    Use:

    ```python
    path.write_text(quote)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    quote = "Small steps repeated consistently lead to mastery."

    path = Path("quote.txt")

    path.write_text(quote)
    ```

#### Why This Exercise Exists

Programs rarely write hardcoded values directly to files.

More commonly, information is generated, collected, or calculated before being saved.

This exercise reinforces the idea that file contents can come from variables and program data.

---

## **Compose**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

### PATHLIB-WF-11

#### Scenario

You have a notes file:

```
notes.txt
```

You want to create a backup copy of the file.

The backup should be saved as:

```
notes-backup.txt
```

#### Objective

Read the contents of:

```
notes.txt
```

Write the contents to:

```
notes-backup.txt
```

#### Success Criteria

Your program should:

- Read the original file
- Create a new file
- Save the same contents to the new file

#### Need a Hint?

??? tip "Small Hint"

    You'll need to work with two Path objects.

??? tip "Stronger Hint"

    Read from one file and write to another.

??? tip "Almost There"

    Combine:

    ```python
    read_text()
    ```

    and

    ```python
    write_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    source = Path("notes.txt")
    backup = Path("notes-backup.txt")

    contents = source.read_text()

    backup.write_text(contents)
    ```

#### Why This Exercise Exists

Copying information from one file to another is a common automation task.

Many backup and export tools follow this basic pattern.

---

### PATHLIB-WF-12

#### Scenario

You are preparing documentation for a project.

The original file is:

```
README.md
```

You want to create a version where all text is converted to uppercase.

The result should be saved as:

```
README-UPPERCASE.md
```

#### Objective

Read the file contents.

Convert the text to uppercase.

Write the transformed contents to a new file.

#### Success Criteria

Your program should:

- Read the source file
- Convert the text
- Save the transformed text to a new file

#### Need a Hint?

??? tip "Small Hint"

    Strings can be transformed before being written.

??? tip "Stronger Hint"

    Convert the contents after reading them.

??? tip "Almost There"

    Use:

    ```python
    contents.upper()
    ```

##### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    source = Path("README.md")
    destination = Path("README-UPPERCASE.md")

    contents = source.read_text()

    destination.write_text(contents.upper())
    ```

#### Why This Exercise Exists

Many automation scripts transform data before saving it.

Examples include formatting, cleaning, converting, and preparing reports.

---

### PATHLIB-WF-13

#### Scenario

You maintain a list of tasks stored in:

```
tasks.txt
```

You want to create a summary report showing how many tasks are stored in the file.

The report should be written to:

```
task-summary.txt
```

#### Objective

Read the task file.

Count the number of lines.

Write a report containing the total.

#### Success Criteria

Your report should contain text similar to:

```text
Total Tasks: 12
```

#### Need a Hint?

??? tip "Small Hint"

    Read the file before analyzing it.

??? tip "Stronger Hint"

    Count the lines using `splitlines()`.

??? tip "Almost There"

    Use:

    ```python
    len(contents.splitlines())
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    tasks_file = Path("tasks.txt")
    report_file = Path("task-summary.txt")

    contents = tasks_file.read_text()

    task_count = len(contents.splitlines())

    report = f"Total Tasks: {task_count}"

    report_file.write_text(report)
    ```

#### Why This Exercise Exists

Many automation tools analyze information and save the results in a report.

This pattern appears frequently in monitoring, reporting, and analytics systems.

---

### PATHLIB-WF-14

#### Scenario

You have a documentation file:

```
guide.txt
```

You want to create a quick file summary.

The summary should contain:

- Filename
- Character Count
- Line Count

The summary should be saved in:

```
guide-summary.txt
```

#### Objective

Inspect the file.

Read the contents.

Generate a summary.

Write the summary to a new file.

#### Success Criteria

The summary file should contain information similar to:

```text
Filename: guide.txt
Characters: 348
Lines: 21
```

#### Need a Hint?

??? tip "Small Hint"

    You'll need both path information and file contents.

??? tip "Stronger Hint"

    Read the file once and reuse the contents.

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

    source = Path("guide.txt")
    summary_file = Path("guide-summary.txt")

    contents = source.read_text()

    summary = f"""Filename: {source.name}
    Characters: {len(contents)}
    Lines: {len(contents.splitlines())}
    """

    summary_file.write_text(summary)
    ```

#### Why This Exercise Exists

Most real-world automation combines multiple capabilities.

This exercise combines:

- Path inspection
- File reading
- Content analysis
- File writing

into a single workflow.

---

### PATHLIB-WF-15

#### Scenario

You are building a simple report generator.

A file contains meeting notes:

```
meeting-notes.txt
```

Create a new report file containing:

- The original filename
- The number of lines
- The full contents of the meeting notes

Save the report as:

```
meeting-report.txt
```

#### Objective

Read the meeting notes.

Generate a report.

Write the report to a new file.

#### Success Criteria

The report should contain information similar to:

```text
Filename: meeting-notes.txt

Line Count: 8

Contents:
<Project Notes Here>
```

#### Need a Hint?

??? tip "Small Hint"

    Create a new string containing all of the report information.

??? tip "Stronger Hint"

    Use both path information and file contents.

??? tip "Almost There"

    Combine:

    ```python
    path.name
    path.read_text()
    len(contents.splitlines())
    ```

    before using:

    ```python
    write_text()
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    source = Path("meeting-notes.txt")
    report_file = Path("meeting-report.txt")

    contents = source.read_text()

    report = f"""Filename: {source.name}

    Line Count: {len(contents.splitlines())}

    Contents:
    {contents}
    """

    report_file.write_text(report)
    ```

#### Why This Exercise Exists

This exercise serves as a capstone for the Compose section.

It combines:

- Creating paths
- Inspecting paths
- Reading files
- Analyzing file contents
- Writing files

into a realistic reporting workflow.

This is very similar to the kinds of automation scripts developers build in real projects.

---

## **Automate**

🚧 Section Needs Elaboration (See creating-files.md for example)

---

### PATHLIB-WF-16

#### Scenario

You are creating daily journal files.

You have several journal entries stored in a list.

Each entry should be saved to its own file.

#### Objective

Create the following files:

```
- day-1.txt
- day-2.txt
- day-3.txt
```

Write one journal entry to each file.

#### Success Criteria

Your program should:

- Create multiple Path objects
- Create multiple files
- Write a different journal entry to each file

#### Need a Hint?

??? tip "Small Hint"

    You will need to create several files.

??? tip "Stronger Hint"

    A loop can help create files automatically.

??? tip "Almost There"

    Create a Path object for each filename and use:

    ```python
    path.write_text(...)
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    entries = [
        "Learned about pathlib.",
        "Practiced reading files.",
        "Practiced writing files."
    ]

    for index, entry in enumerate(entries, start=1):
        path = Path(f"day-{index}.txt")
        path.write_text(entry)
    ```

#### Why This Exercise Exists

Automation frequently involves generating multiple files rather than manually creating each one.

This exercise demonstrates how repetitive tasks can be automated with loops.

---

### PATHLIB-WF-17

#### Scenario

You maintain several meeting notes files.

You want to create a summary file that lists the number of lines in each meeting note.

#### Objective

Read multiple files and write a summary report named:

```
meeting-summary.txt
```

#### Success Criteria

The summary file should contain information similar to:

```text
meeting-1.txt: 8 lines
meeting-2.txt: 12 lines
meeting-3.txt: 5 lines
```

#### Need a Hint?

??? tip "Small Hint"

    Read each file before generating the report.

??? tip "Stronger Hint"

    Build the report text gradually.

??? tip "Almost There"

    Store report lines in a list and join them together before writing.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("meeting-1.txt"),
        Path("meeting-2.txt"),
        Path("meeting-3.txt"),
    ]

    report_lines = []

    for path in paths:
        contents = path.read_text()
        report_lines.append(
            f"{path.name}: {len(contents.splitlines())} lines"
        )

    report = "\n".join(report_lines)

    Path("meeting-summary.txt").write_text(report)
    ```

#### Why This Exercise Exists

Many automation scripts process multiple files and save the results as a report.

This pattern appears frequently in reporting and analytics tools.

---

### PATHLIB-WF-18

#### Scenario

You maintain several documentation files.

You want to create backup copies automatically.

For every source file:

- README.md
- guide.md
- setup.md

create a backup file ending with:

```text
.backup
```

#### Objective

Read each file and write its contents to a corresponding backup file.

#### Success Criteria

Your program should create:

```text
README.backup
guide.backup
setup.backup
```

with the same contents as the original files.

#### Need a Hint?

??? tip "Small Hint"

    Each source file needs a matching destination file.

??? tip "Stronger Hint"

    Read from one file and write to another.

??? tip "Almost There"

    Use:

    ```python
    read_text()
    ```

    and

    ```python
    write_text()
    ```

    inside a loop.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    files = [
        Path("README.md"),
        Path("guide.md"),
        Path("setup.md"),
    ]

    for source in files:
        backup = Path(f"{source.stem}.backup")

        backup.write_text(
            source.read_text()
        )
    ```

#### Why This Exercise Exists

Many practical tools create backups before making changes.

This exercise demonstrates a common automation workflow involving reading and writing files.

---

### PATHLIB-WF-19

#### Scenario

You are creating a keyword report.

Several files contain project notes.

You want to identify which files mention:

```text
Python
```

and save the matching filenames in a report.

#### Objective

Read multiple files and create:

```
python-files.txt
```

containing the names of files that mention Python.

#### Success Criteria

The report should contain something similar to:

```text
notes-1.txt
notes-3.txt
```

#### Need a Hint?

??? tip "Small Hint"

    Search the contents of each file.

??? tip "Stronger Hint"

    Collect matching filenames before writing the report.

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
        Path("notes-1.txt"),
        Path("notes-2.txt"),
        Path("notes-3.txt"),
    ]

    matches = []

    for path in paths:
        contents = path.read_text()

        if "Python" in contents:
            matches.append(path.name)

    report = "\n".join(matches)

    Path("python-files.txt").write_text(report)
    ```

#### Why This Exercise Exists

Many automation tools search large collections of files and save the results for later review.

This combines reading, searching, and writing capabilities.

---

### PATHLIB-WF-20

#### Scenario

You are building a simple document inventory tool.

The tool should inspect and analyze several files and generate a report describing them.

#### Objective

For each file:

- Read the contents
- Count characters
- Count lines

Generate a report file named:

```
inventory-report.txt
```

#### Success Criteria

The report should contain information similar to:

```text
notes.txt
Characters: 145
Lines: 8

ideas.txt
Characters: 421
Lines: 19
```

#### Need a Hint?

??? tip "Small Hint"

    Process one file at a time.

??? tip "Stronger Hint"

    Build a report string as you go.

??? tip "Almost There"

    Combine:

    ```python
    path.name
    len(contents)
    len(contents.splitlines())
    ```

    before writing the report.

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    paths = [
        Path("notes.txt"),
        Path("ideas.txt"),
        Path("tasks.txt"),
    ]

    report_lines = []

    for path in paths:
        contents = path.read_text()

        report_lines.append(
            f"""\
    {path.name}
    Characters: {len(contents)}
    Lines: {len(contents.splitlines())}
    """
        )

    report = "\n".join(report_lines)

    Path("inventory-report.txt").write_text(report)
    ```

#### Why This Exercise Exists

This exercise acts as a capstone for the Writing Files capability.

It combines:

- Path creation
- Path inspection
- File reading
- Content analysis
- Report generation
- File writing

into a realistic automation workflow.

Many real-world developer tools follow this exact pattern of gathering information and exporting the results to a report.
