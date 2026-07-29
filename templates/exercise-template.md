# Exercise Template

All exercises within Python Mastery Path follow a common structure.

The goal is not merely to learn syntax.

The goal is to understand:

- Why a capability is useful
- When it would be used
- How Python helps solve a practical problem

For this reason, every exercise begins with a realistic scenario rather than a purely technical task.

---

## Standard Exercise Template

```markdown
## EXERCISE-ID

### Scenario

A realistic problem or situation.

### Objective

The concrete task.

### Success Criteria

What must be achieved.

### Hint 1

Very vague.

### Hint 2

More specific.

### Hint 3

Almost enough to solve the exercise.

### Solution

(Optional - hidden later)
```

---

## Example

### PATHLIB-CP-01

#### Scenario

You keep personal notes in a text file located at:

notes/todo.txt

Before Python can work with this file, your program needs a way to represent its location on disk.

This is one of the most common uses of pathlib.

#### Objective

Create a Path object representing:

notes/todo.txt

Store it in a variable named `path`.

Print the path to the console.

#### Success Criteria

Your program should:

- Create a Path object
- Store it in a variable named `path`
- Print the path

#### Hint 1

The pathlib module provides a `Path` class.

#### Hint 2

Import `Path` from `pathlib`.

#### Hint 3

Create a Path object using:

```python
Path("notes/todo.txt")
```

---

## Exercise Philosophy

Exercises should make learners think:

> "I've encountered this problem before."

or:

> "That sounds useful."

rather than:

> "Here's another coding challenge."

Every exercise should teach a capability through a practical problem.

Problem
↓
Task
↓
Solution

rather than

Task
↓
Task
↓
Task
