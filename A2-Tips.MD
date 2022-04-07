# Tips for Take-Home Assessment 2

## Table of Content

- [Checklist](#checklist)
- [Structure and Design](#structure-and-design)
- [Use of Language Features](#use-of-language-features)
- [Document and Readability](#document-and-readability)

---

## Checklist

Steps to draw the Space Needle:

1. Break the Space Needle into chunks.

   > A chunk should have the same characters. Each character in a chunk should have a definitive pattern (increasing, decreasing, or neither).

   Example figure:

   ```
     *
    ***
   *****
    ***
     *
   ```

   In the above example, you cannot draw the whole diamond figure as one chunk. This is caused by the pattern of `*` character changing halfway (increasing to decreasing). Here is a suggestion how to break the diamond figure into two chunks:

   Chunk one:

   ```
     *
    ***
   *****
   ```

   Chunk two:

   ```
    ***
     *
   ```

   > Don't forget to keep an eye on repeated chunks in the Space Needle!

2. For each chunk, create the skeleton loop first. (the outer loop and the inner loop)

   A skeleton code may look like the following:

   ```java
   for (int line = 1; line <= ...; line++) {
       System.out.print("||");
       for (int j = 1; j <= ...; j++) {
           System.out.println("*");
       }

       for (int j = 1; j <= ...; j++) {
           System.out.println(".");
       }

       for (int j = 1; j <= ...; j++) {
           System.out.println("\\");
       }

       System.out.println("||");
   }
   ```

   You will later fill in the `...` in your loop with some formula!

3. For each chunk, analyze each character in that chunk to determine whether they are line, SIZE, both, or neither dependent.

4. After determining whether each character's dependency, find the formula for each character using the `y = mx + b` formula.

   > Remember to solve for `m` (slope) first before solving `b`.

5. Don't forget to do the ASCII Art portion!

---

## Structure and Design

Ideally, you should have:

1. 4 - 5 methods other than the main method.
2. Main should remain a concise summary of your program (no `println()` and it should not only contain 1 method call)
3. Watch out for any redundant method call!

---

## Use of Language Features

Things to watch out for:

1. Blank line should be printed using `System.out.println();` instead of `System.out.println("");`
2. Beware of two or more `print` and/or `println` that can be combined together.

   Example I:

   ```java
   System.out.print("hello");
   System.out.println();
   ```

   Should instead be written as:

   ```java
   System.out.println("hello");
   ```

   Example II:

   ```java
   System.out.print("hello");
   System.out.print("hahaha");
   ```

   Should instead be written as:

   ```java
   System.out.print("hellohahaha");
   ```

3. You should <u>**not**</u> need a 3 level nested loop.

   > A 3 level nested loop is a for-loop inside a for-loop, which is inside a for-loop. Example:

   ```java
   for (int i = 1; i <= 3; i++) {
       for (int j = 1; j <= 4; j++) {
           for (int k = 1; k <= 5; k++) {

           }
       }
   }
   ```

4. You should not have a loop that runs only once. Remember a loop is used to repeat a task. Any task that is only executed once all the time does not need a loop.

---

## Document and Readability

1. Header, class, and method comment.
2. Proper indentation.
3. Descriptive method name.
4. Descriptive variable name.
5. Method and variable name must be **camelCased**.
6. Blank line between one method and another.
7. All lines should be shorter than 100 characters.
8. Use descriptive variable name for your for-loop variable counter. If you want to use one letter variable name, make sure to follow the i-j-k convention.
   > The i-j-k convention is explained in [Additional-Style-Guide.MD](/Additional-Style-Guide.MD)
