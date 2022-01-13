# Theory

## Variable Scope

---

The scope of a variable (where the variable exist and can be used) depends on the **_direct parent_** where the variable is declared.

Take a look at the example below:

```java
public class Demo {
    public static void main(String[] args) {
        int someNumber = 6;
        for (int i = 1; i <= 4; i++) {
            String someText = "hello";
        }
    }

    public static void createVariable() {
        double someDecimal = 4.5;
    }
}
```

The scope of the variables above is listed below:

1. `int someNumber` is declared directly inside the main method, meaning it only exist in the main method. Since the for-loop is inside the main method, you _can_ access or use `someNumber` from for-loop.
2. `int i` and `String someText `is declared directly inside the for-loop, meaning it only exist inside the for-loop. You cannot access or use them before or after the for-loop.
3. `double someDecimal` is declared in the `createVariable()` method, meaning it only exist in the `createVariable()` method. You can only access or use it inside the `createVariable()` method.

---

## Class Constant

---

Class constant is a variable that exist and can be used in the whole class. However, the value of class constant cannot be changed once it is set.

Here is how to declare a class constant:

```java
public class Demo {
    // Template:
    // public static type CONSTANT_NAME = value;

    // Example:
    public static final int HEIGHT = 180;
    public static final String CODE = "algbx23";

    public static void main(String[] args) {
        // some code here
    }
}
```

> Note that class constant shoudl be placed outside of any method. Stylisticly, it is preferrable to declare it right after you declare your class and before you declare your main method.

> Note that the value of `HEIGHT` and `CODE` in the above example cannot be changed from any of your method. If you try to do so, you will encounter a compiler error.
