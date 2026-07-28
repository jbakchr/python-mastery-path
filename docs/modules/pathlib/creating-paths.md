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

---

## **Apply**

### PATHLIB-CP-05

#### Objective

Create a Path object representing:

```text
projects
```

Then create another Path object representing:

```text
projects/python
```

using path joining.

#### Hint 1

Create the base path first.

#### Hint 2

Path objects can be combined.

#### Hint 3

Look for the `/` operator.

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
