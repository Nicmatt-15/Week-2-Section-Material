# Additional Style Guide

## Unnecessary Loop

---

Take a look at the example below:

```java
for (int i = 1; i < 2; i++) {
    System.out.println("hello");
}
```

Remember that the purpose of a for-loop is to repeat a task multiple times. If your for-loop runs only 1 time **every time**, it defeats the purpose of having a for-loop in the first place.

The above code can be rewritten as:

```java
System.out.println("hello");
```

---

## Lines over 100 characters

---

Before submitting your work in Ed, make sure that all lines of **_your comments and your code_** are below 100 characters long _(indentation included_).

The easiest way to find if you have long lines or not (in Ed) is:

1. Paste your code in Ed
2. Click your cursor at the end of the longest line (visually) in your code.
3. Take a look at the bottom of your page:
   ![Screen-Shot-2022-01-13-at-08-55-29.png](https://i.postimg.cc/MH22Shmx/Screen-Shot-2022-01-13-at-08-55-29.png)

> If the image does not load, please use the following link: https://postimg.cc/njkwKSWw

4. Right above the Console text, there are two numbers separated by a colon.
5. The left number (in the above image, it is 4) is the line number. You do not have to pay attention to this.
6. The right number (in the above image, it is 37) is the line length. Your line length should not exceed 100. If your line is above 100 characters long, it should be broken into two more lines.

---

## Combinable print

---

Take a look at the code below:

```java
System.out.print("#");
System.out.println();
```

Should instead be combined to:

```java
System.out.println("#");
```

---

## i-j-k Naming Convention

---

If you decide to use non-descriptive variable name for your for-loop counter, it should strictly follow the i-j-k convention. The rules are as follow:

1. Your outer loop counter variable should be named i
2. Your second level loop counter variable should be named j
3. Your third level loop counter variable should be named k

Take a look at the example below:

```java
for (int i = 1; i <= 4; i++) { // outer loop
    for (int j = 1; j <= 3; j++) { // 2nd level loop
        System.out.print("hello");

        for (int k = 1; k <= 9; k++) { // 3rd level loop
            System.out.print("hi");
        }
    }

    for (int j = 1; j <= 6; j++) { // 2nd level loop
        System.out.print("aloha");
    }

    System.out.println();
}
```

---

## Screaming Case

---

Class constant name should be SCREAMING*CASED. Every letter should be capitalized and an underscore (*) is used to separate one word from another.

```
Correct example:
PAGES_IN_BOOK
```

```
Incorrect example:
1. pages_in_book
2. pagesInBook
3. PagesInBook
```
