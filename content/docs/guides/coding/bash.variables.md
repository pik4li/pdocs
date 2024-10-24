---
title: "bash.Variables"
description: ""
summary: ""
date: 2024-10-16T09:12:17+02:00
lastmod: 2024-10-16T09:12:17+02:00
draft: false
weight: 999
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Bash parameter expansion is a powerful feature that allows you to manipulate and retrieve the value of variables in a variety of ways. Here’s a detailed explanation of some common and advanced forms of parameter expansion:

### 1. **Default Values**

- **`${VARIABLE:-default}`**: If `VARIABLE` is unset or null, it substitutes `default`. Otherwise, it returns the value of `VARIABLE`.

  ```bash
  myvar=
  echo "${myvar:-Hello}"  # Outputs "Hello" because myvar is empty

  ```

- **`${VARIABLE:=default}`**: If `VARIABLE` is unset or null, it sets it to `default` and returns the value.

  ```bash
  echo "${myvar:=Hello}"  # myvar is set to "Hello"

  ```

- **`${VARIABLE:+value}`**: If `VARIABLE` is set and not null, it returns `value`. Otherwise, it returns nothing.

  ```bash
  myvar="world"
  echo "${myvar:+Hello}"  # Outputs "Hello"

  ```

- **`${VARIABLE:?message}`**: If `VARIABLE` is unset or null, it prints an error message (`message`) to stderr and exits the script. If no message is provided, a default message is shown.

  ```bash
  echo "${myvar:?myvar is not set}"  # Prints an error if myvar is not set

  ```

### 2. **Substring Operations**

- **`${VARIABLE:offset}`**: Extracts a substring starting from `offset`. If `offset` is negative, it starts from the end of the string.

  ```bash
  myvar="abcdef"
  echo "${myvar:2}"  # Outputs "cdef" (starts from index 2)

  ```

- **`${VARIABLE:offset:length}`**: Extracts a substring starting from `offset` with the specified `length`.

  ```bash
  echo "${myvar:1:3}"  # Outputs "bcd" (3 characters starting from index 1)

  ```

### 3. **String Length**

- **`${#VARIABLE}`**: Returns the length of the string stored in `VARIABLE`.

  ```bash
  echo "${#myvar}"  # Outputs "6" (length of "abcdef")

  ```

### 4. **Pattern Substitution**

- **`${VARIABLE#pattern}`**: Removes the shortest match of `pattern` from the start of `VARIABLE`.

  ```bash
  myvar="file.txt"
  echo "${myvar#*.}"  # Outputs "txt" (removes "file.")

  ```

- **`${VARIABLE##pattern}`**: Removes the longest match of `pattern` from the start.

  ```bash
  myvar="path/to/file.txt"
  echo "${myvar##*/}"  # Outputs "file.txt" (removes "path/to/")

  ```

- **`${VARIABLE%pattern}`**: Removes the shortest match of `pattern` from the end of `VARIABLE`.

  ```bash
  echo "${myvar%.txt}"  # Outputs "file" (removes ".txt")

  ```

- **`${VARIABLE%%pattern}`**: Removes the longest match of `pattern` from the end.

  ```bash
  myvar="path/to/file.txt"
  echo "${myvar%%/*}"  # Outputs "path" (removes everything after the first "/")

  ```

### 5. **Search and Replace**

- **`${VARIABLE/pattern/replacement}`**: Replaces the first match of `pattern` with `replacement`.

  ```bash
  myvar="apple, orange, apple"
  echo "${myvar/apple/grape}"  # Outputs "grape, orange, apple"

  ```

- **`${VARIABLE//pattern/replacement}`**: Replaces **all** matches of `pattern` with `replacement`.

  ```bash
  echo "${myvar//apple/grape}"  # Outputs "grape, orange, grape"

  ```

- **`${VARIABLE/#pattern/replacement}`**: If `pattern` matches the beginning of `VARIABLE`, replace it with `replacement`.

  ```bash
  echo "${myvar/#apple/grape}"  # Replaces only if "apple" is at the start

  ```

- **`${VARIABLE/%pattern/replacement}`**: If `pattern` matches the end of `VARIABLE`, replace it with `replacement`.

  ```bash
  echo "${myvar/%apple/grape}"  # Replaces only if "apple" is at the end

  ```

### 6. **Remove Variable Content**

- **`${VARIABLE@operator}`**: An advanced feature that applies transformations based on the operator. Common ones are:

  - `@Q`: Quote the value (useful for shell-safe strings).
  - `@A`: Convert to an array.

  ```bash
  myvar="Hello"
  echo "${myvar@Q}"  # Outputs "'Hello'" (quoted)

  ```

### Practical Examples

#### 1. **Setting Default Values**

```bash
user="${USER:-defaultuser}"

```

#### 2. **Check if a Variable is Empty**

```bash
: "${myvar:?myvar is required but not set}"

```

#### 3. **String Manipulation**

- Remove file extension:

```bash
  filename="document.txt"
  echo "${filename%.txt}"

```

- Get the last part of a path:

```bash
  path="/usr/local/bin"
  echo "${path##\*/}" # Outputs "bin"

```
