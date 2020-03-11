---
layout: post
title:  "LISP: Glad my school taught it"
date:   2019-02-10 13:00:00 -0700
category: [programming]
---

A lot of classmates will get frustrated with `(lisp)`, hate the class or professor for including it in the syllabus, and continue to hate it after the class. Although I despised it while trying to make an interpreter, it actually gave me a better understanding of functional programming, and especially recursion.

<!--more-->

<image style="float:right;width:200px;height:auto;" src="https://upload.wikimedia.org/wikipedia/commons/f/f4/Lisplogo.png" />


### What is LISP?

[LISP](https://en.wikipedia.org/wiki/Lisp_(programming_language)) is a collection of programming languages, with a heavy focus on functional programming and mathematical rules, rather than a computer's von Neumann architecture. In the course offered at UCI, we used a subset of LISP commonly referred to as [Pure LISP](http://www.wbricken.com/pdfs/02teach/05proglang/14-purelisp.pdf) that excludes most of the programming ideas that we students love. 

In our course, we were limited to the following built-in functions:

* car
* cdr
* cons
* quote
* cond
* defun
* basic arithmetic (add, mul, sub)
* basic predicates (null, atom, numberp, stringp, symbolp, listp)


Notice: no `setq`, which means, no variables can be defined. No `if` - that is replaced with basic `cond` statements. And most importantly, a ton of parentheses. 

## Why LISP?

Realistically, LISP teaches us functional programming, dynamic scoping, and efficient use of recursive functions. This can all be done with any contemporary multi-paradigm programming languages. _So why LISP?_

The most obvious answer: annoying students by having to use parentheses.

But there is a slight difference between using this and, for example, JavaScript. JavaScript can, theoretically, do whatever you want it to do. Object oriented, functional, declarative, imperative even, and so on. LISP is strictly restricted to functional (especially when you consider Pure LISP). 

### "Simple" Operations

Learning Python first at UCI makes us take so many operations for granted. For example, getting the length of a list. Sure, there is `len` functions, and _maybe_ we resort to counting with a simple `for` or `while` loop...

But in LISP:

```
(defun length (x)
    (cond
        ((null x) 0)
        ((atom x) 1)
        ((lisp x)
            (+ 1 (length (cdr x)))
        )
    )
)
```

Just for statistics sake, 29% of the characters above are parentheses. Appreciation of modern syntax and functions aside, we actually see a simple example of recursion executed beautifully with LISP. We see the fundamentals of comparison functions based on how `cond` evaluates and "returns" a function. These core ideas translate to creating a live interpreter.

# LISP Interpreter

> An interpreter, at it's very core, is simply an infinite loop that: gets input from the user, evaluates it, and prints a result back.

Implementing this interpreter then means focusing on one function, and considering different "built-in" cases: `eval`. We must be able to evaluate atoms, lists, and basic function calls like `car` or `cdr` and especially `defun`. Being able to handle `defun` function calls means any other function can be defined within the interpreter, and saved in the "association list".

## Key Learning Goals

There were three main points that students should have recognized during the implementation of the LISP interpreter.

#### 1. Defining/Executing Functions

When handling `defun` conditions on the evaluation function, we realized that a "function" is a series of statements. That seems obvious - in fact, that's probably one of the first things they teach us in computer science.

But when we see that in LISP, we can create lists and traverse them recursively, and each "statement" is just another line that needs to be evaluated. Defining and running a function is incredibly simple.

To define: "set" the function name as a variable to refer to a list of statements.

To execute: Recursively execute each statement.

**Wait:** What about control flow? No problem, `cond` is just another statement that has another list of statements. Each statement looks generally like `((null x) 0)` which simply translates to: _Evaluate the first element (null x), and if its true, evaluate the second element (in this case, 0)_.

#### 2. Parameter-Argument Assignments

Implementing function calls using LISP was interesting. Every student in the class has seen and wrote functions that have parameters. Some of us even know that arguments are evaluated in certain orders.

But implementing function calls in LISP allows us to truly understand "local scope". When running a function, we create a new _association list_ that is essentially a store for variables, and parameters are assigned to the evaluated arguments. Using those parameters in the function simply looks up the value in the temporary association list. 

Going back to other programming languages, and knowing whether they are [lexical or dynamic scoped](https://www.geeksforgeeks.org/static-and-dynamic-scoping/), gives us a greater understanding of the implementation, and less likely to make simple mistakes.

#### 3. Recursion!

With the limitations placed by LISP, we also gain a lot of confidence on creating and tracing recursive functions. Looping and static lookup of values were nonexistent in our version of LISP.

Whether we are searching for a value in a list, evaluating a function's, or even assigning arguments to parameters in function calls, the same hand ful of recursive functions were used. 

In my implementation of LISP interpreter, I only had 11 function definitions built in. A simple function call would result in hundreds of recursive calls. Tracing through these to debug was horrifying. But it allows me to appreciate true recursive function ideals.

## Should we still learn LISP?

> Note: I'm going to leave out talking about Artificial Intelligence. One of the main contemporary uses of LISP is AI, but I don't have any experience or relevant knowledge on that. I am only speaking from the point of view of a software engineering student.

https://image.slidesharecdn.com/lisppivorak-190913103822/95/lisplots-of-irritating-superfluous-parentheses-1-638.jpg?cb=1568371117

LISP was an old and annoying programming language to use. But after playing with it, I can start to see the influence on modern programming languages like Python and Perl. Having this experience, in my opinion, gives you a better mastery of those modern languages.

If nothing else, simply having more experience with functional programming and recursion is benefit enough. Restricting our viewpoint to only consider functional solutions to any problems allows us to understand recursive problems easier. It is a skill just like any other, and more practice will result in better mastery. Using LISP simply forces you to think a certain way; many of us are swayed into imperative programming solutions.