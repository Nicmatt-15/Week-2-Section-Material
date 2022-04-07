# Basic of Nested For Loop

Recall that the fourth part of a for-loop (the part in between the opening and closing curly bracket) is a place where _(almost)_ any code written will be repeated. This includes a for-loop (Nested For-Loop)!

> A nested for loop is a for-loop inside a for loop!

---

## Table of Content

- [Tracing a Nested For Loop](#tracing-a-nested-for-loop)

---

## Tracing a Nested For Loop

Give the for-loop code below:

```java
for (int i = -1; i <= 1; i++) {
    for (int j = 0; j < 3; j++) {
        System.out.print("hello");
    }

    for (int j = 3; j < 7; j++) {
        System.out.print("aloha");
    }

    System.out.println();
}
```

Here is how java will read and run your code (note that this assume you have understood well how a single for-loop is run):

1. Line 1 -> `i = -1`.

   Line 1 -> `-1 < 1` is true

2. Line 2 - 4 -> Prints out `"hello"` 3 times on the same line
3. Line 6-8 -> Prints out `"aloha"` 4 times on the same line
4. Line 10 -> Move the output cursor to the new line

---

4. Back to Line 1 -> `i++`

   Line 1 -> `i = 0 (-1 + 1)`

   Line 1 -> `0 < 1` is true

5. Line 2 - 4 -> Prints out `"hello"` 3 times on the same line
6. Line 6-8 -> Prints out `"aloha"` 4 times on the same line
7. Line 10 -> Move the output cursor to the new line

---

10. Back to Line 1 -> `i++`

    Line 1 -> `i = 1 (0 + 1)`

    Line 1 -> `1 < 1` is false

11. Quits the for-loop

> Notice that java will finish one inner loop first before moving on to the next inner loop. In this case, java will run the loop from line 2 - 4 until it finishes before running the loop from line 6-8.

> `System.out.println()` will produce a blank line if there is a String printed before it using `println`. If the last String is printed using `print` instead, `System.out.println()` will only move the output cursor to the next line instead of making a blank line. See example below.

---

Using `println` before `println()`:

```java
public class Demo {
    public static void main(String[] args) {
        System.out.println("hello");
        System.out.println();
        System.out.println("aloha");
    }
}
```

Output of the above code:

```
hello

aloha
```

---

Using `print` before `println()`:

```java
public class Demo {
    public static void main(String[] args) {
        System.out.print("hello");
        System.out.println();
        System.out.println("aloha");
    }
}
```

Output of the above code:

```
hello
aloha
```
