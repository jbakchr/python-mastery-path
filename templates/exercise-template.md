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

### EXERCISE-ID

#### Scenario

A realistic problem or situation.

#### Objective

The concrete task.

#### Success Criteria

What must be achieved.

#### Hints

??? tip "Small Hint"

    A gentle nudge that helps learners think in the right direction
    without revealing the solution.

??? tip "Stronger Hint"

    More specific guidance that points toward the relevant capability.

??? tip "Almost There"

    A hint that nearly reveals the solution while still requiring
    some thought from the learner.

#### Solution

??? success "Show Solution"

    ```python
    # Example solution
    ```

#### Why This Exercise Exists

Explain why this capability matters, when it would be useful,
and how it connects to real-world Python development.

---

## Example

### PATHLIB-CP-01

#### Scenario

You keep personal notes in a text file located at:

```text
notes/todo.txt
```

Before Python can work with this file, your program needs a way to represent its location on disk.

This is one of the most common uses of pathlib.

#### Objective

Create a Path object representing:

```text
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

    Create a Path object using the file location:

    ```text
    notes/todo.txt
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

---

## Hint Philosophy

Hints should be progressive.

Small Hint
    ↓
Stronger Hint
    ↓
Almost There
    ↓
Solution

The goal is to encourage learners to think and experiment before
receiving increasingly specific guidance.

Hints should guide discovery rather than immediately reveal answers.