# Basic of For Loop

## Table of Content

- [Elements of For Loop](#elements-of-for-loop)
- [Tracking For Loop](#tracking-for-loop)

---

## Elements of For Loop

There are 4 important elements of a for-loop:

1. A counter variable
2. A conditional statement (a statement that evaluates to true or false)
3. A statement that updates the value of the counter variable after every interation
4. The code inside the for-loop itself

Take a look at the picture below:
![Screen-Shot-2022-01-12-at-19-03-38.png](https://i.postimg.cc/kG8Lf7L8/Screen-Shot-2022-01-12-at-19-03-38.png)

> If the image above does not load, please use this link: https://postimg.cc/H8YSL1Ys

Explanation:

1. The counter variable is a variable that helps keep track of what iteration number your loop is on. The number that you set the counter variable equal to (in the picture above, it is 1) is the starting number of your for-loop.
   > Generally, people set the starting value of their for-loop as 0 or 1, but you can set it to any value that you want.
2. The second part is a conditional statement, a statement that helps keep track of whether the loop should still run or stop. **If the conditional statement evaluates to true, then the loop will keep running. Otherwise, it will stop running.**
3. The third part is a statement that updates the value of the counter variable after each iteration has finished. _For example, after the first iteration has finished, `i++` increases the value of i from 1 to 2._
4. The code in between the opening and closing curly bracket is the code that will be repeated over and over again.

Take a closer look at the 2nd and 3rd point.

The third point mentions that after every iteration, `i++` will increase the value of i by 1. When the value of i is 1, 2, 3, or 4, the statement `i <= 4` is `true` and the loop keeps going.

However, once the value of i reaches 5, `i <= 4` is false because `5 <= 4` is false. This causes the loop to stop and lets java run the code below the for-loop.

---

## Tracking For Loop

Given the following for-loop:

```java
for (int i = -1; i < 2; i++) {
    System.out.println("Enters Loop!");
}
```

Here is how the above for-loop will run:

1. Line 1 -> `i = -1`.

   Line 1 -> `-1 < 2` is true

2. Line 2 -> Prints out `"Enters Loop!"`
3. Line 3 -> Indicates the end of one iteration

---

4. Back to Line 1 -> `i++`

   Line 1 -> `i = 0 (-1 + 1)`

   Line 1 -> `0 < 2` is true

5. Line 2 -> Prints out `"Enters Loop!"`
6. Line 3 -> Indicates the end of one iteration

---

7. Back to Line 1 -> `i++`

   Line 1 -> `i = 1 (0 + 1)`

   Line 1 -> `1 < 2` is true

8. Line 2 -> Prints out `"Enters Loop!"`
9. Line 3 -> Indicates the end of one iteration

---

10. Back to Line 1 -> `i++`

    Line 1 -> `i = 2 (1 + 1)`

    Line 1 -> `2 < 2` is false

11. Quits the for-loop
