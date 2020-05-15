---
layout: post
title: What are the differences between Java and Scheme
date: 2020-05-14 02:29 -0400
description: " Object vs Procedure"
author: tatiana_azulay
---
<h3>Declarative vs Imperative programming</h3>
<p>In <strong>imperative programming</strong> we use statements to change the state of the program and consecutive statements describe the control flow (do something, then do something else).<br />
<strong>Declarative programming</strong> paradigm focuses on the logic and not on the control flow. In declarative programming we describe how the result should look like but not how it needs to be accomplished.<br />
<strong>Declarative languages include logic languages (e.g. Prolog), functional languages (e.g. Haskell, Scheme), template-based (XSLT) and database (SQL).<br />
Imperative languages include scripting languages (Perl, Python, PHP,…) and object-oriented (C++, Java, C#,…)</strong></p>
Scheme and Java belong to different programming paradigms.<br />
<h3>So what features are different between those two languages?</h3>
<table style="width:100%">
  <tr>
    <th>Scheme features:</th>
    <th>Java features:</th>
  </tr>
  <tr>
    <td>Variables in Scheme are dynamically typed (no need to declare the type of the variable when you define it)</td>
    <td>Variables in Java are statically typed (the type must be declared when variable is defined)</td>
  </tr>
  <tr>
    <td>Recursion (no loop statements)</td>
    <td>Iterative loops</td>
  </tr>
  <tr>
    <td>Scheme is rule-based and uses pattern matching,
high-order functions, some lazy evaluation (data is evaluated when it is used)
</td>
    <td>Java uses abstract data types, inheritance overriding, polymorphism</td>
  </tr>
  <tr>
    <td>lexical-scope (the interpreter searches in lexically surrounding definitions (lambdas and lets))</td>
    <td>dynamic scope (the interpreter searches for a local definition of a variable in the frame of function. If it isn't found, the interpreter searches up the calling stack for a definition.)</td>
  </tr>

</table>

Java is object oriented and Scheme is procedure oriented.
Procedures are fundamental blocks of Scheme programs. Recursion is also a procedure in Scheme on contrast with java implementations of recursion as an iterative method.<br />
Consider a function which adds two numbers<br />
<strong>Java recursive implementation may look like:</strong><br />
static int add (int x, int y)  
{if(y==0) <br />
        return x; <br /> 
    else <br /> 
        return (1+add (x, y-1)); <br />
} <br />
<hr>
<p>Scheme as a functional language supports optimized tail recursion as it allows to pass a function as an argument and return as a value.</p>
<strong>Consider the same function which adds two numbers implemented with tail recursion in Scheme:</strong>
<hr>
(define (succ x)(+ x 1))<br />
(define (prev x)(- x 1))<br />
(define (add x y)<br />
  (if (eq? y 0) x (succ (add x (prev y)))))<br />
  <hr>
<p>What’s the difference? Lets add 2 and 3</p>
<strong>If we look at the steps of the java recursive implementation, we’ll see:</strong>
<hr>
add (2 3)<br/>
add (3 2)<br/>
add (4 1)<br/>
add (5 0)<br/>
<hr>
<strong>If we look at the steps of Scheme function, we’ll see something like this:</strong>
<hr>
(add 2 3)<br/>
(succ (add 2 2))<br/>
(succ (succ (add 2 1)))<br/>
(succ (succ (succ (add 2 0))))<br/>
(succ (succ (succ 3)))<br/>
(succ (succ 4))<br/>
(succ 5)<br/>
<hr>
Though the result is the same the process of computation is different as Scheme tail recursion optimization uses memory differently and allows to prevent stack overflow.


