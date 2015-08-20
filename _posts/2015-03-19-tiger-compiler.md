---
layout:     post
title:      Tiger Compiler
date:       2015-03-19 23:42:42
summary:    Tiger Language Compiler
categories: school
---

The Tiger compiler is a 5-month project in a team of 4 students, which aims an
advanced use of C++ and a better understanding of compiler theory.

The idea came from Modern Compiler Implementation by Andrew W. Appel.
Since the book is only discussing implementations in C, Java and ML, EPITA, and
especially Akim wanted to do it in a more advanced and powerful language.
**C++**.

The [LRDE](https://www.lrde.epita.fr/~tiger/assignments) is helping us
with some code.

## Front end
The first part of the compiler is the front end.

### Lexer / Parser
The lexer was created using **Flex**, and the parser using **Bison**.

### Semantic analysis
This part of the Tiger project consists in analysing the source code,
and verify the validity of the code, before translating it to
an intermediate representation.

This part includes binding, where definitions are associated to utilizations
and type checking, where the type compatibility is verified.
We added function overloading, loop-desugar and function pruning and inlining.

### Translation
The translation part is going to generate an intermediate representation of our
program, from a semanticly correct AST.

The IR language is the Tree language, used in Appel's books.

I am also working on a LLVM generation from the AST.

## Back end

### Low-level translation (Canonicalization)
From the High-level intermediate language (HIR), we are going
to remove the nested instructions and generate a flat list of instructions, in
order to aim lower-level languages, like assembly.

Some optimizations were added at this phase, like constant expression reduction.

### Instruction selection
From the LIR, we are going to generate MIPS and x86 assembly.
Some members of my group worked on a ARM and SPARC target.

### Liveness analysis
This is where the fun part begins. For now, we have unlimited registers and a
list of instructions.

This part, is transforming this list of instructions in a flow control graph.

This graph is the base of the liveness analysis stage of the compiler.
This allows us to know when each temporary is alive, so that we can generate
an interference graph, allowing us to allocate registers properly.

### Register allocation
The last stage of Tiger is the most important and algorithmically challenging
stage.

During this stage, we have to allocate the temporaries a register each,
put some of them on the stack if needed (spilling), and finish our
Tiger Compiler.

More information about the biggest Tiger community, [LRDE](https://www.lrde.epita.fr/~tiger/tiger).
