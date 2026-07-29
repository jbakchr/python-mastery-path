# **pathlib - Creating Paths**

## **Overview**

The exercises in this section focus on creating and combining `Path` objects.

By completing these exercises you will learn how to:

- Create Path objects
- Combine paths
- Work with relative paths
- Work with absolute paths

---

## **Discover**

### PATHLIB-CP-01

#### Scenario

You keep personal notes in a text file located at:

```
notes/todo.txt
```

Before Python can work with this file, your program needs a way to represent its location on disk.

This is one of the most common uses of pathlib.

#### Objective

Create a Path object representing:

```
notes/todo.txt
```

Store it in a variable named `path`.

Print the path to the console.

#### Success Criteria

Your program should:

- Create a Path object
- Store it in a variable named `path`
- Print the path

#### Need a Hint?

??? tip "Small Hint"

    The pathlib module provides a `Path` class.

??? tip "Stronger Hint"

    Import `Path` from `pathlib`.

??? tip "Almost There"

    ```python
    Path("notes/todo.txt")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("notes/todo.txt")

    print(path)
    ```

#### Why This Exercise Exists

This is the first and most fundamental pathlib capability.

Before Python can work with a file or directory, your program needs a way to represent its location.

Path objects provide that representation and serve as the foundation for everything else you will do with pathlib.

---

### PATHLIB-CP-02

#### Scenario

You keep project documentation inside a repository.

One file you frequently update is:

```text
docs/README.md
```

Before your Python script can work with that file, it needs a way to represent its location.

#### Objective

Create a Path object representing:

```text
docs/README.md
```

Store it in a variable named path.

Print the path.

#### Success Criteria

Your program should:

- Create a Path object
- Store it in a variable named `path`
- Print the path

#### Need a Hint?

??? tip "Small Hint"

    The location should become a Path object.

??? tip "Stronger Hint"

    Import Path from pathlib.

??? tip "Almost There"

    ```python
    Path("docs/README.md")
    ```

#### Solution

??? success "Show Solution"

    ```python
    from pathlib import Path

    path = Path("docs/README.md")

    print(path)
    ```

#### Why This Exercise Exists

Introduces another common real-world file location without adding new concepts.

---

### PATHLIB-CP-03

#### Scenario

You are writing an automation script for your Downloads folder.

The script will eventually organize files, but first it needs a way to represent the folder itself.

The folder is:

```text
Downloads
```

#### Objective

Create a Path object representing:

```text
Downloads
```

Store it in a variable named downloads_path.

Print the path.

#### Success Criteria

Your program should:

- Create a Path object representing a directory
- Store it in downloads_path
- Print the path

#### _Hint 1_

Paths can represent folders as well as files.

#### _Hint 2_

You still use the Path class.

#### _Hint 3_

```python
Path("Downloads")
```

#### Why This Exercise Exists

Many beginners subconsciously think paths are only files.

This teaches:

```
Path → file OR directory
```

which is an important mental model.

---

### PATHLIB-CP-04

#### Scenario

You are working on a backup script.

The script needs access to a file located inside several folders:

```
projects/python/backups/config.json
```

Before the file can be read, your program must represent its location.

#### Objective

Create a Path object representing:

```
projects/python/backups/config.json
```

Store it in a variable named config_path.

Print the path.

#### Success Criteria

Your program should:

- Create the Path object
- Store it in config_path
- Print the path

#### _Hint 1_

A path can contain multiple nested directories.

#### _Hint 2_

Pass the full location to Path.

#### _Hint 3_

```
Path("projects/python/backups/config.json")
```

#### Why This Exercise Exists

Introduces deeper directory structures without introducing any new API.

### PATHLIB-CP-05

#### Scenario

You have several markdown files inside a documentation project.

One of them is:

```
guides/getting-started.md
```

You want Python to keep track of that file's location.

#### Objective

Create a Path object representing:

```
guides/getting-started.md
```

Store it in a variable named guide_path.

Print the path.

#### Success Criteria

Your program should:

- Create the Path object
- Store it in guide_path
- Print the path

#### Hint 1

Represent the file location using a Path object.

#### Hint 2

Import Path.

#### Hint 3

```python
Path("guides/getting-started.md")
```

#### Why This Exercise Exists

Reinforces the core capability through repetition.

---

## **Apply**

### PATHLIB-CP-06

#### Scenario

You are writing a script that works inside a project directory.

The project folder is:

```
my-project
```

Inside it is a documentation file:

```
README.md
```

You want to create the file path by combining the project directory and file name.

#### Objective

Create:

```
my-project/README.md
```

using multiple Path components.

Store the result in readme_path.

Print the path.

#### Success Criteria

Your program should:

- Create a Path object for the project directory
- Build the final file path
- Print the result

#### _Hint 1_

A Path object can be combined with other path parts.

#### _Hint 2_

Look for an operator that joins paths together.

#### _Hint 3_

```
project_dir / "README.md"
```

#### Why This Exercise Exists

Introduces path composition.

---

### PATHLIB-CP-07

#### Scenario

You keep your notes inside:

```
notes/
```

Today's note is:

```
meeting.txt
```

Rather than writing the full path manually, you decide to build it from smaller pieces.

#### Objective

Create:

```
notes/meeting.txt
```

using the `/` operator.

Store the result in note_path.

Print the path.

#### Success Criteria

Your program should:

- Create a directory path
- Append a filename
- Print the final path

#### _Hint 1_

Create the folder path first.

#### _Hint 2_

Use / to add another path component.

#### _Hint 3_

```
notes_dir / "meeting.txt"
```

#### Why This Exercise Exists

Reinforces the composition concept.

---

### PATHLIB-CP-08

#### Scenario

You are building a documentation tool.

Documentation files live inside:

```
docs/
```

The user chooses which page to open.

The page name is stored in:

```
page_name = "installation.md"
```

Your program needs to build the full path.

#### Objective

Create:

```
docs/installation.md
```

using page_name.

Store the result in page_path.

Print the path.

#### Success Criteria

Your program should:

- Use the provided variable
- Build the path dynamically
- Print the path

#### _Hint 1_

Variables can be combined with Path objects.

#### _Hint 2_

The / operator works with strings.

#### _Hint 3_

```
docs_dir / page_name
```

#### Why This Exercise Exists

Introduces dynamic path building.

This feels much closer to real software.

---

### PATHLIB-CP-09

#### Scenario

You are building a backup utility.

Backups are stored inside:

```
backups
```

Each backup belongs to a specific year.

The year is stored in:

```
year = "2026"
```

You need to create:

```
backups/2026
```

#### Objective

Build the path using multiple components.

Store the result in backup_dir.

Print the path.

#### Success Criteria

Your program should:

- Create the root backup directory
- Add the year folder
- Print the final path

#### _Hint 1_

Each folder can be added separately.

#### _Hint 2_

Use / more than once if needed.

#### _Hint 3_

```
Path("backups") / year
```

#### Why This Exercise Exists

Shows that directories can be built dynamically just like files.

---

### PATHLIB-CP-10

#### Scenario

You are organizing project files.

A configuration file is stored in:

```
projects/demo/config/settings.json
```

Rather than writing the entire path as a string, you decide to build it from meaningful components.

#### Objective

Construct:

```
projects/demo/config/settings.json
```

using multiple path segments.

Store the result in settings_path.

Print the path.

#### Success Criteria

Your program should:

- Create the path step by step
- Use the / operator
- Print the final result

#### _Hint 1_

Each folder can be its own path component.

#### _Hint 2_

Chain multiple / operations.

#### _Hint 3_

```
Path("projects") / "demo" / "config" / "settings.json"
```

#### Why This Exercise Exists

Demonstrates how larger paths can remain readable and maintainable.

---

## Compose

### PATHLIB-CP-11

#### Scenario

You are building a project from inside its root directory.

Your script should work no matter where the project is located on a user's computer.

The current working directory should be used as the starting point.

A log file will live in:

```
logs/app.log
```

inside the project.

#### Objective

Create a path representing:

```
[current directory]/logs/app.log
```

Store the result in log_path.

Print the path.

#### Success Criteria

Your program should:

- Obtain the current working directory
- Build the rest of the path using /
- Print the final path

#### _Hint 1_

pathlib can provide the current directory.

#### _Hint 2_

Look for a method on Path related to the current working directory.

#### _Hint 3_

```
Path.cwd()
```

#### Why This Exercise Exists

Introduces one of the most useful sources of paths in real programs.

---

### PATHLIB-CP-12

#### Scenario

You are creating a personal note-taking application.

Each user should store notes inside their own home directory.

The note file should be:

```
notes/today.md
```

inside the user's home folder.

#### Objective

Create a path representing:

```
[home directory]/notes/today.md
```

Store the result in note_path.

Print the path.

#### Success Criteria

Your program should:

- Obtain the user's home directory
- Build the notes path
- Print the result

#### _Hint 1_

pathlib can locate a user's home directory.

#### _Hint 2_

Look for a method named home.

#### _Hint 3_

```
Path.home()
```

#### Why This Exercise Exists

Introduces another extremely common starting point.

---

### PATHLIB-CP-13

#### Scenario

You are building a backup utility.

The user chooses a backup name:

```
backup_name = "photos"
```

All backups live inside:

```
backups/
```

under the current working directory.

#### Objective

Create a path representing:

```
[current directory]/backups/photos
```

Store it in backup_path.

Print the result.

#### Success Criteria

Your program should:

- Use Path.cwd()
- Use backup_name
- Build the final path dynamically

#### _Hint 1_

Start with the current directory.

#### _Hint 2_

Add each path component separately.

#### _Hint 3_

```
Path.cwd() / "backups" / backup_name
```

#### Why This Exercise Exists

Combines dynamic values with a runtime-generated base path.

---

### PATHLIB-CP-14

#### Scenario

You are writing a documentation generator.

The project root is the current working directory.

Documentation files are stored in:

```
docs/
```

The page name is provided as:

```
page_name = "installation.md"
```

#### Objective

Create a path representing:

```
[current directory]/docs/installation.md
```

Store the result in page_path.

Print the path.

#### Success Criteria

Your program should:

- Get the current directory
- Use the provided filename variable
- Build the complete path

#### _Hint 1_

The current directory becomes the base path.

#### _Hint 2_

Combine multiple components using /.

#### _Hint 3_

```
Path.cwd() / "docs" / page_name
```

#### Why This Exercise Exists

Very similar to what static site generators and documentation tools do.

---

### PATHLIB-CP-15

#### Scenario

You are creating a script that stores application settings.

Settings belong in:

```
.config/myapp/settings.json
```

inside the user's home directory.

#### Objective

Create a path representing:

```
[home directory]/.config/myapp/settings.json
```

Store the result in settings_path.

Print the path.

#### Success Criteria

Your program should:

- Obtain the home directory
- Build a nested path
- Print the final result

#### _Hint 1_

Start with the user's home directory.

#### _Hint 2_

Add each folder separately.

#### _Hint 3_

```
Path.home() / ".config" / "myapp" / "settings.json"
```

#### Why This Exercise Exists

Shows how multiple path-building techniques combine in a realistic application.

---

## Automate

### PATHLIB-CP-16

### Scenario

You are building a note-taking application.

A user wants note files for several topics:

```python
topics = [
    "python",
    "pathlib",
    "automation"
]
```

All notes should be stored inside:

```
notes/
```

Each note should have a .md extension.

Objective

Create and print the following paths:

```
notes/python.md
notes/pathlib.md
notes/automation.md
```

Generate them using a loop.

#### Success Criteria

Your program should:

- Use the provided list
- Build paths dynamically
- Print each path

#### _Hint 1_

Each topic becomes part of a filename.

#### _Hint 2_

Use a loop to process every topic.

#### _Hint 3_

```python
Path("notes") / f"{topic}.md"
```

#### Why This Exercise Exists

Introduces automated path generation.

---

### PATHLIB-CP-17

#### Scenario

You are creating a backup utility.

Backup folders should be created for multiple years:

```python
years = [
    "2024",
    "2025",
    "2026"
]
```

All backups live inside:

```
backups/
```

#### Objective

Create and print paths representing:

```
backups/2024
backups/2025
backups/2026
```

#### Success Criteria

Your program should:

- Use the supplied list
- Build directory paths dynamically
- Print every path

#### _Hint 1_

Each year becomes a directory name.

#### _Hint 2_

Combine the base directory with each year.

#### _Hint 3_

```python
Path("backups") / year
```

#### Why This Exercise Exists

Shows that path generation applies equally to files and directories.

---

### PATHLIB-CP-18

#### Scenario

You are building a documentation generator.

The project contains multiple pages:

```python
pages = [
    "index.md",
    "installation.md",
    "configuration.md"
]
```

All documentation files belong inside:

```
docs/
```

#### Objective

Create and print the path for every page.

Expected output:

```
docs/index.md
docs/installation.md
docs/configuration.md
```

#### Success Criteria

Your program should:

- Loop through every page
- Create a Path object for each page
- Print each generated path

#### _Hint 1_

Each page is already a complete filename.

#### _Hint 2_

Combine a shared directory with each page.

#### _Hint 3_

```python
Path("docs") / page
```

#### Why This Exercise Exists

Introduces the concept of a reusable base path.

---

### PATHLIB-CP-19

#### Scenario

You are building a photo organizer.

Photos should be stored inside folders named after their year.

You have:

```python
years = ["2024", "2025"]
photos = [
    "vacation.jpg",
    "birthday.jpg"
]
```

For every year and every photo, generate a path.

#### Objective

Create and print paths such as:

```
photos/2024/vacation.jpg
photos/2024/birthday.jpg
photos/2025/vacation.jpg
photos/2025/birthday.jpg
```

#### Success Criteria

Your program should:

- Use both provided lists
- Generate every path combination
- Print all generated paths

#### _Hint 1_

You may need nested loops.

#### _Hint 2_

Build the path one component at a time.

#### _Hint 3_

```python
Path("photos") / year / photo
```

#### Why This Exercise Exists

Introduces multi-level automated path generation.

---

### PATHLIB-CP-20

#### Scenario

You are building a simple project scaffolding tool.

New projects should contain:

```
src/
tests/
docs/
```

A project name is provided:

```python
project_name = "my_app"
```

Your script should generate the paths that would exist inside the project.

#### Objective

Create and print:

```
my_app/src
my_app/tests
my_app/docs
```

using the provided project name and a list of directory names.

#### Success Criteria

Your program should:

- Build paths dynamically
- Reuse the project name
- Generate all required paths

#### _Hint 1_

The project name becomes the root directory.

#### _Hint 2_

Loop through the required directories.

#### _Hint 3_

```python
Path(project_name) / directory
```

#### Why This Exercise Exists

This is the first exercise that feels like a genuine automation task rather than merely a learning exercise.
