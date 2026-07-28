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

#### Hint 1

A Path object can be combined with other path parts.

#### Hint 2

Look for an operator that joins paths together.

#### Hint 3

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

#### Hint 1

Create the folder path first.

#### Hint 2

Use / to add another path component.

#### Hint 3

```
notes_dir / "meeting.txt"
```

#### Why This Exercise Exists

Reinforces the composition concept.

---



---

### PATHLIB-CP-06

#### Objective

Create this path without writing the full string directly:

```text
reports/2026/july/report.txt
```

Build it by combining smaller path segments.

#### Hint 1

Create the root directory first.

#### Hint 2

Combine additional segments step by step.

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
