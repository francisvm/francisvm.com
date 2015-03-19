---
layout:     post
title:      Tiger Compiler
date:       2015-03-19 23:42:42
summary:    Tiger Language Compiler
categories: school
---

The Tiger compiler is a 5-month project in a team of 3 students, which aims an advanced use of C++.

The idea came from Modern Compiler Implementation by Andrew W. Appel.
Since the book is only discussing implementations in C, Java and ML, EPITA, and especially
Akim wanted to do it in a more advanced and powerful language. **C++**.

The [LRDE](https://www.lrde.epita.fr/~tiger/assignments) is helping us with some basic code.

## Front end
The first part of the compiler is the front end.

### Lexer / Parser
The lexer was created using **flex**, and the parser using **bison**.

### AST builder
Building an Abstract Syntax Tree for the Tiger language is based on the parsing done by **bison**.

### Pretty-Printer
The pretty printer is only a debug phase. It is one of the most important phases in order
to succeed the other levels.

It is based on the design pattern **Visitor**. The **Visitor** in *TC* gives
an entry point into the AST, and allows us to operate on the nodes without being intrusive.
Almost all the parts of the front end are based on the visitor.

### Binder
The binder is the part where an utilisation of a variable, function or type
is associated to its definition.

It is heavily based on the **Visitor** design pattern, as well.


So far, Tiger is a work in progress.

More information about the biggest Tiger community, [LRDE](https://www.lrde.epita.fr/~tiger/tiger).
