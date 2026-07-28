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

##### _Hint 1_

The pathlib module provides a `Path` class.

##### _Hint 2_

Import `Path` from `pathlib`.

##### _Hint 3_

Create a Path object using the string:

```python
"notes/todo.txt"
```

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

#### _Hint 1_

The location should become a Path object.

#### _Hint 2_

Import Path from pathlib.

#### _Hint 3_

```python
Path("docs/README.md")
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

# Compose

## PATHLIB-CP-05

### Objective

Write a function:

```python
def build_project_path(project_name):
```

that returns:

```text
projects/<project_name>
```

Examples:

```python
build_project_path("lx")
```

returns:

```text
projects/lx
```

### Hint 1

Accept a string parameter.

### Hint 2

Create a Path object.

### Hint 3

Combine path segments.

---

# Automate

## PATHLIB-CP-06

### Objective

Create a small script that prints the following paths:

```text
notes/
projects/
downloads/
archive/
```

using Path objects rather than plain strings.

### Hint 1

Create multiple Path objects.

### Hint 2

Store them in a list.

### Hint 3

Loop through the list and print each path.
