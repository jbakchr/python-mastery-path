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

#### _Objective_

Create a Path object representing the following file:

```text
notes/todo.txt
```

Store it in a variable named `path`.

#### _Hint 1_

The pathlib module provides a `Path` class.

#### _Hint 2_

Import `Path` from `pathlib`.

#### _Hint 3_

Create a Path object using the string:

```python
"notes/todo.txt"
```

---

### PATHLIB-CP-02

#### Objective

Create a Path object representing:

```text
projects/python/app.py
```

Print the path object.

#### Hint 1

The path does not need to exist.

### Hint 2

Path objects can be printed.

---

# Apply

## PATHLIB-CP-03

### Objective

Create a Path object representing:

```text
projects
```

Then create another Path object representing:

```text
projects/python
```

using path joining.

### Hint 1

Create the base path first.

### Hint 2

Path objects can be combined.

### Hint 3

Look for the `/` operator.

---

## PATHLIB-CP-04

### Objective

Create this path without writing the full string directly:

```text
reports/2026/july/report.txt
```

Build it by combining smaller path segments.

### Hint 1

Create the root directory first.

### Hint 2

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
