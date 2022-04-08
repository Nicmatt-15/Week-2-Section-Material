# Line Theory

## Table of Content

- [Single Line Uniform Pattern](#single-line-uniform-pattern)
- [Single Line Multiple Pattern](#single-line-multiple-pattern)
- [Multiple Line Uniform Pattern](#multi-line-uniform-pattern)
- [Multiple Line Changing Pattern](#multi-line-changing-pattern)
- [Scalable Figure](#scalable-figure)

---

## Single Line Uniform Pattern

In this week's material, we learned that we can use a for-loop to repeat a task multiple times. One of the application of for-loop is printing a line multiple times. For example, if we want to print out the pattern:

```java
****
```

We can make a for-loop that run 4 times and prints out 1 `*` in each iteration.

```java
for (int asterisk = 1; asterisk <= 4; asterisk++) {
    System.out.print("*");
}
```

> Notice the use of `System.out.print(...)` instead of `System.out.println(...);`. If we use `System.out.println(...);`, each `*` will be printed on its own line instead of all `*` printed on the same line.

---

## Single Line Multiple Pattern

When we need to print out pattern like:

```
****//////
```

We would need one for-loop for each different character. The code to print the above output would look like:

```java
for (int asterisk = 1; asterisk <= 4; asterisk++) {
    System.out.print("*");
}

for (int slash = 1; slash <= 6; slash++) {
    System.out.print("/");
}
```

---

## Multi Line Uniform Pattern

When we want to print out multiple lines of figure, we will need to use a nested for-loop. For example, if we want to print out:

```java
****
****
****
****
****
****
```

Our code would look like:

```java
for (int line = 1; line <= 6; line++) {
    for (int asterisk = 1; asterisk <= 4; asterisk++) {
        System.out.print("*");
    }
}
```

> Key observation: Notice that the number `6` in the outer loop indicates how many line of output we want to print. The number `4` in the inner loop indicates how many character we want to print.
>
> This key observation will be true for more complicated figures!

---

## Multi Line Changing Pattern

What if we want to print out a different number of `*` in each line? Something that looks like:

```java
********
******
****
**
```

Since we are printing a different amount of `*` in each line, we cannot do something like:

```java
for (int line = 1; line <= 4; line++) {
    for (int asterisk = 1; asterisk <= 8; asterisk++) {
        System.out.print("*");
    }
}
```

The number 8 in the inner for-loop means our code is going to print out 8 `*` in all the lines. In fact, we cannot put a different number to repace 8 because your program will still print out the same amount of `*` in each line.

We will replace the number 8 using a formula. Here is two things that you should know about the formula:

1. It will be in the form `y = mx + b` (linear line formula).
2. The variable `line` controlled by the outer for-loop will be used in the formula. The reason behind this is the number of `*` printed in a line depends on what line number it is (depends on the value of line).

The variables in the formula `y = mx + b` are as follow:

```
y: the number of characters in a line
m: how many characters increase / decrease going from one line to another line
x: what affects the number of characters in a line
b: some number that fulfills the equation
```

Since we know that the value of the variable `line` affects the number of characters in a line, we can write the formula `y = mx + b` as `y = m * line + b`.

The goal here is to solve for `m` and `b`. Here are the steps:

1. Solve for `m` first. The number of `*` decreases by 2 (in the example above) going from one line to another. This means that `m` will be `-2`.

   > The - (negative) value for `m` indicates that the number of character from line to line is decreasing.
   >
   > If the number of character from line to line is increasing, the value of `m` will be + (positive).

2. To solve for b, pick a line and plug in the value for `y` and `line`. For example, if I am choosing the first line of the output, then:

   ```
   y = 8 (there are 8 * in the first line)
   line = 1 (the first line)
   m = -2 (solved from step 1)
   ```

   Solving for b:

   ```
   y = m * line  + b
   8 = -2 * 1 + b
   8 = -2 + b
   8 + 2 = b
   10 = b
   ```

3. Our formula becomes:

   ```
   y = -2 * line + 10
   ```

4. We will take the right side of the equation (after the `=` sign and place it in our inner loop). The code will become:

```java
for (int line = 1; line <= 4; line++) {
    for (int asterisk = 1; asterisk <= -2 * line + 10; asterisk++) {
        System.out.print("*");
    }
}
```

---

## Scalable Figure

One of the hardest part of Take-Home Assessment 2 is figuring out how to scale your Space Needle using a class constant.

To scale your Space Needle using a class constant properly, you have to make sure that any characters that increase / decrease when the value of the class constant change must be scaled properly using your class constant.

> In Space Needle, you're asked to name your class constant "SIZE". For this reason, the explanation below would refer to the class constant as "SIZE".

Let's take a look at the two figures below:

```
SIZE = 3

!!!<>..<>!!!
!!<>....<>!!
!<>......<>!
```

```
SIZE = 4

!!!!<><>!!!!
!!!<>..<>!!!
!!<>....<>!!
!<>......<>!
```

Key observations:

Even though it looks like the whole figure grows bigger when the value of SIZE increase, only some things scale up when the value of SIZE increase. Here are the list of changes:

1. The number of lines being printed scales up.
2. The number of `!` on the same line between SIZE = 3 and SIZE = 4 scales up. The number of `!` also changes from one line to the next line.
3. The number of `<>` on the same line <u>**doesn't**</u> scale up between SIZE = 3 and SIZE = 4. The number of `<>` also <u>**doesn't**</u> change from one line to another.
4. The number of `.` on the same line <u>**doesn't**</u> scale up between SIZE = 3 and SIZE = 4. However, the number of `.` change from one line to the next line.

From the changes above, we can infer that:

1. The number of lines depends on the value of SIZE (SIZE dependent).
2. The number of `!` depends on both the value of SIZE and which line it is (both dependent).
3. The number of `<>` does not depend on SIZE and which line it is (neither dependent).
4. The number of `.` depends on the line, but not the SIZE (line dependent).

> To find if a character is <u>**line**</u> dependent, you should compare the number of character from one <u>**line**</u> to another (for the same SIZE).

> To find if a character is <u>**SIZE**</u> dependent, you should compare the number of character from one <u>**SIZE**</u> to another (for the same line).

Here are the formulas that you should use:

1. If a character is line dependent, the formula is `y = m * line + b`
2. If a character is SIZE dependent, the formula is `y = m * SIZE + b`
3. If a character is both dependent, the formula is `y = m1 * line + m2 * SIZE + b`
4. If a character is neither dependent, you don't need to find a formula. **You also do not need a for-loop to print out the character**

Solving for all formulas in the example above:

1. The number of output lines

   ```
   When SIZE = 3, we print out 3 lines of output
   When SIZE = 4, we print out 4 lines of output

   We don't really need any formula here. It's somewhat obvious that the number of output lines = SIZE.
   ```

2. The number of `!`

   ```
   Dependent on both line and SIZE. Use formula:
   y = m1 * line + m2 * SIZE + b

   Solve for either m1 or m2 first.

   -------------------------------------------------
   When the line increase by 1, the number of ! decrease by 1. This means the value of m1 = -1

   -------------------------------------------------
   When SIZE = 3, the first line has 3 ! sign
   When SIZE = 4, the first line has 4 ! sign

   When the SIZE increase by 1, the number of ! for the same line increase by 1. This means the value of m2 = 1 (positive).

   -------------------------------------------------
   To solve for b, you can choose any line at any SIZE. Let's say I want to choose the first line at SIZE = 4.

   line = 1
   SIZE = 4
   y = 4 (There are 4 continuous ! sign in the first line)

   y = m1 * line + m2 * SIZE + b
   4 = -1 * 1    + 1  * 4    + b
   4 = -1        + 4         + b
   4 = 3 + b
   4 - 3 = b
   1 = b

   The final formula here is:
   y = -1 * line + SIZE + 1
   ```

3. The number of `<>` doesn't depend on SIZE and line. No formula needed.

4. The number of `.`

   ```
   The number of . depends on the line, so we use:
   y = m * line + b

   Solve for m first

   -------------------------------------------------
   When the line increase by 1, the number of . increase by 2. This means the value of m is 2 (positive).

   -------------------------------------------------
   To solve for b, choose any line that you want. If we want to choose the third line (for SIZE = 3):

   line = 3 (the third line)
   y = 6 (there are 6 continous . (dot) sign  in the third line)

   y = 2 * line + b
   6 = 2 * 3    + b
   6 = 6 + b
   6 - 6 = b
   0 = b

   The final formula is:
   y = 2 * line + 0 which can be written as y = 2 * line
   ```

Piecing all these formulas together, we get the code:

```java
for (int line = 1; line <= SIZE; line++) { // number of output line = SIZE
    // In a single line, we will print:
    // The ! first
    for (int exclamation = 1; exclamation <= -1 * line + SIZE + 1; exclamation++) {
        System.out.print("!");
    }

    // Followed by the <> -> no need loop since neither dependent
    System.out.print("<>");

    // Followed by the . -> line dependent
    for (int dot = 1; dot <= 2 * line; dot++) {
        System.out.print(".");
    }

    // Followed by the <> again -> no need loop since neither dependent
    System.out.print("<>");

    // Followed by another !
    for (int exclamation = 1; exclamation <= -1 * line + SIZE + 1; exclamation++) {
        System.out.print("!");
    }

    // Move output to a new line once we are done printing one line
    System.out.println();
}
```

> At this point of the quarter, you don't have the tool to reduce the redundancy between one inner loop and another inner loop.
