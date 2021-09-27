**CPEN 221 / Fall 2020 / Lab 4B**

# Debugging Some Poetry

## Debugging

The purpose of this lab activity is **debugging**. You will gain additional experience reading provided code, understanding it, reviewing it, and debugging some problems associated with it. There will also be discussion on Java's support for `static` members of classes. (This aspect is relevant to the exercise on cutting and splicing DNA strands too.)

## Look at poems for “song”.

There are a variety of ways to determine the quality of source code and to identify “code smells.” Some of these are:

- Don’t repeat yourself.
- Use comments where needed.
- Fail fast.
- Avoid magic numbers.
- One purpose for each variable.
- Use good names.
- Don’t use global variables.
- Use coherent methods.
- Methods should return results, not print them.
- Use whitespace to help in reading.

Think about the following aspects:

- What is bad about how this code is organized, its style, what’s included or missing, …?
- What is good about how this code is organized, its style, what’s included or missing, …?
- What is confusing about this code or individual lines of code?

## First-line Bug

Our poems all have a strange common feature on their first line:

`[something] metric linear unit`.

How can we debug the problem?

### Trace backward

- Click on the return type of a method to see all the places that method might return.
- Hover over a method to see `Javadoc` documentation. In IntelliJ IDEA you can bring up the documentation via the **View → Quick Documentation** menu (or the associated keyboard shortcut).

### `System.out.println`

- One of the most basic and most useful debugging tools.
- Add unambiguous tags to your output to avoid confusion.

### Debugger

- Add a breakpoint, then step over and into method calls.
- Inspect values of the variables that are in scope.

We don’t have to understand everything about the code we’re debugging. At the same time, we need to recognize all of our assumptions, and be ready for them to turn out wrong.

**The most powerful debugging tool at your disposal is clear, logical thinking.**

You will encounter bugs that require you to understand technical intricacies. But most of good software engineering is about careful, creative, logical thinking: in design, in code, in testing, and in debugging.

When reading code, hope the author has tried their best to communicate with you, not just the machine.

- Grow your understanding of the code in stages: don’t try to understand an entire program at once.
- Over time, develop an intuition about kinds of bugs, how they manifest, and where to hunt them down.

When writing code, try your best to communicate with the reader (maybe future you), not just the machine.

### What next?

With our understanding of the code so far, is this bug reproducible? If an input noun always produces the same 0th word ID → synset → gloss, the bug is reproducible.

What are a couple of different ways you might try to fix this bug?

## Out-of-Bounds Bug

**Look at poems for words such as “gun” and “meter”.**

Sometimes, but not always, one of these words will generate an exception. How can we debug the problem?

### Stack trace

- Click on a `FileName.java:line` link to jump to the source.

### Debugger

- Run the program under the debugger, let it catch the exception.

### Don’t ignore, don’t fix, reproduce

- Don’t ignore the bug and hope it doesn’t come back.
- Don’t jump to fix the bug without understanding.

*This bug is not always reproducible.* We don’t want to guess whether we have a reproducible test case, we want to be sure.

*Think about how you can reproduce the bug. Then fix the bug!*

## Illegal Argument Bug

**Look at a poem called “babel”.**

Is this exception our bug, or a bug in the library throwing the exception?

We can use `println` or the debugger to discover that we call `sense( )` with the empty string. That’s our bug.

If you already know regular expressions, fix the bug. If not — you’ll see them at some point!

---

#### Any program, no matter how small, can have bugs

But if we know we’re going to find another bug every n lines, it would be much better to write a 0.5n–line program than a 50n–line program!

---

## What should you do?

Fix the problems associated with `UBCPoet`. Address these issues:

- code style and smells;
- the first-line bug;
- the out-of-bounds bug;
- the illegal argument bug.