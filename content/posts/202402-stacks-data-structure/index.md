+++
title = "Stacks Data Structure"
date = 2024-02-25T00:08:52+03:00
draft = false
tags = ["data-structures-and-algorithms", "stacks", "java"]
series = ["Data Structures and Algorithms"]
series_order = 4
+++

## Introduction

Stacks are powerful data structures with a simple yet versatile nature. They operate on the `Last In, First Out (LIFO)` principle, making them ideal for tasks like:

- Undo/redo functionality in application
- Implementing compilers (syntax checking)
- Evaluating arithmetic expressions (e.g., 1 + 2 \* 3)
- Building navigation systems (e.g., forward and back buttons)

### Undestanding stacks

Think of stacks as a pile of books. You can stack them on top of each other, but you can only interact with or remove the top book on the pile. This `LIFO` behaviour translates perfectly to stacks in programming. Elements are added (`pushed`) and removed (`popped`) from the top, making them efficient for scenarios where you revisit actions in reverse order.

## Stack Operations

Stacks support four primary operations:

- `push(item)`: Add an item to the top of the stack.
- `pop()`: Remove the item from the top of the stack.
- `peek()`: Return the item on the top without removing it.
- `isEmpty()`: Check if the stack is empty.

## Runtime Complexity

Stacks are implemented using either arrays or linked lists. This makes stacks efficient because inserting, removing, or retrieving items at the end of arrays or linked lists is quick. This means that all primary stack operations have a constant runtime complexity of `O(1)`.

## Working with Stacks in Java

In Java, stacks are implemented through the `Stack` class in the `java.util` package. The following code snippet demonstrates the practicle usage of stacks in Java.

```java
import java.util.Stack;

public class Main {
  public static void main(String[] args) {
    Stack<Integer> stack = new Stack<Integer>();

    stack.push(10);
    stack.push(20);
    stack.push(30);
    System.out.println(stack); // [10, 20, 30]

    var top = stack.pop();
    System.out.println(top); // 30
    System.out.println(stack); // [10, 20]

    System.out.println(stack.isEmpty()); // false

    top = stack.peek();
    System.out.println(top); // 20
    System.out.println(stack); // [10, 20]
  }
}
```

## Exercise 1: Reversing a String

A common interview question involves reversing a string. This can be efficiently solved using a stack as shown on the snippet below:

```java
import java.util.Stack;

public class StringReverser {
    public String reverse(String input) {
        if (input == null)
            throw new IllegalArgumentException();

        Stack<Character> stack = new Stack<>();

        // Push each character from the input string onto the stack
        for (char ch : input.toCharArray())
            stack.push(ch);

        // Pope each character from the stack and append to the reversed string
        StringBuffer reversed = new StringBuffer();
        while (!stack.empty())
            reversed.append(stack.pop());

        // Convert the StringBuffer into a string and return the result
        return reversed.toString();
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        String str = "abcd";
        StringReverser reverser = new StringReverser();
        var result = reverser.reverse(str);
        System.out.println(result); // Output: "dcba"
    }
}
```

## Exercise 2: Balanced Expressions

Another common interview question involves checking the balance of brackets within a string, that is, ensuring that each opening bracket has a corresponding closing bracket and that no closing bracket lacks an opening bracket pair. For instance, the expression "(1 + 2)" is balanced, as each opening bracket is appropriately paired with a closing bracket. Similarly, the expression "(1 + [3 * (2 + 1)] + 10)" is balanced since each bracket in the expression has a corresponding closing bracket. On the contrary, expressions like ")1 + 2(" and "((1 + 2)" are unbalanced, as they feature closing brackets without corresponding opening brackets and opening brackets without corresponding closing brackets.

**Solution in Code**

```java
import java.util.Arrays;
import java.util.List;
import java.util.Stack;

public class Expression {
  // Constants for left and right brackets
  private final List<Character> leftBrackets = Arrays.asList('(', '<', '[', '{');
  private final List<Character> rightBrackets = Arrays.asList(')', '>', ']', '}');

  // Checks if the provided string has balanced brackets.
  public boolean isBalanced(String input) {
    Stack<Character> stack = new Stack<>();

    for (char ch : input.toCharArray()) {
      if (isLeftBracket(ch))
        stack.push(ch);
      else if (isRightBracket(ch) && (stack.empty() || !bracketsMatch(stack.pop(), ch)))
        return false;
    }

    return stack.empty();
  }

  // Checks if the character is a left bracket.
  private boolean isLeftBracket(char ch) {
    return leftBrackets.contains(ch);
  }

  // Checks if the character is a right bracket.
  private boolean isRightBracket(char ch) {
    return rightBrackets.contains(ch);
  }

  // Checks if the provided brackets correspond to each other.
    return leftBrackets.indexOf(left) == rightBrackets.indexOf(right);
  }
}
```

**Testing the implementation**

```java
public class Main {
  public static void main(String[] args) {
    Expression exp = new Expression();

    String str1 = "(1 + 2)";
    String str2 = "{1 + 2";
    String str3 = "(([1] + <2>)) [a]";
    String str4 = "((<1] + [2>)) [a]";

    var result1 = exp.isBalanced(str1);
    var result2 = exp.isBalanced(str2);
    var result3 = exp.isBalanced(str3);
    var result4 = exp.isBalanced(str4);

    System.out.println(result1); // Output: true
    System.out.println(result2); // Output: false
    System.out.println(result3); // Output: true
    System.out.println(result4); // Output: false
  }
}
```

## Exercise 3: Building a Stack using an Array

Now that we've grasped the fundamentals of a stack, let's take a hands-on approach and build a stack from scratch. This exercise will deepen our understanding of how stacks work. We'll focus on implementing essential operations like `push`, `pop`, `peek`, and `isEmpty`.

**Solution in Code**

```java
import java.util.Arrays;

public class Stack {
  private int[] items = new int[5]; // Array to store the stack items
  private int count = 0; // Count to track items in the stack

  // Add the given item to the end of the stack
  public void push(int item) {
    if (count == items.length)
      throw new StackOverflowError(); // Throw error if stack is full

    items[count++] = item; // Add item to array and increment count
  }

  // Remove the last item in the stack
  public int pop() {
    if (count == 0)
      throw new IllegalStateException(); // Throw exception if stack is empty

    return items[--count]; // Return last item and decrement count
  }

  // Return the last item in the stack
  public int peek() {
    if (count == 0)
      throw new IllegalStateException(); // Throw exception if stack is empty

    return items[count - 1]; // Return last item
  }

  // Check if the stack is empty
  public boolean isEmpty() {
    return count == 0;
  }

  // Override toString to print items in the stack
  @Override
  public String toString() {
    var content = Arrays.copyOfRange(items, 0, count); // Copy only items in the stack
    return Arrays.toString(content); // Return string representation of items in the stack
  }
}
```

**Testing the implementation**

```java
public class Main {
  public static void main(String[] args) {
    Stack stack = new Stack();

    System.out.println(stack.isEmpty()); // Output: true

    // stack.pop(); // Throws an IllegalStateException exception since the stack is
    // empty

    // Add items to the stack
    stack.push(10);
    stack.push(20);
    stack.push(30);
    stack.push(40);
    stack.push(50);
    // stack.push(60); // Throws a StackOverflowError since the stack is full
    System.out.println(stack); // Output: [10, 20, 30, 40, 50]

    System.out.println(stack.isEmpty()); // Output: false

    System.out.println(stack.pop()); // Output: 50
    System.out.println(stack); // Output: [10, 20, 30, 40]

    System.out.println(stack.peek()); // Output: 40
    System.out.println(stack); // Output: [10, 20, 30, 40]
  }
}
```

## Summary

In this article, we have explored the stack data structure. We have learnt that:

- Stacks operate on the Last In First Out (LIFO) principle.
- Stacks can be implemented using either arrays or linked lists.
- All primary operations in stacks have a runtime complexity of `O(1)`.

## References

- Mosh Hamedani. [Ultimate Data Structures & Algorithms: Part 1](https://codewithmosh.com/p/data-structures-algorithms-part1)
