[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/9YUeXH71)
# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

### Response 

If a researcher claims to have up with a sorting algorithm that sorts in $O(n)$
time without any further assumptions besides that the elements can be compared, 
I would raise an eyebrow. 

As discussed in class, there exists $n!$ 
possible permutations of an array, and by the sorting problem, there must exist
at least one path to get to every permutation; otherwise, the sorting algorithm
fails for that one ordering.

Returning to the only assumption being elements can be compared, each comparison
made is based on the question: "Is $a < b$?" The only two answers from this are "yes"
and "no", so for every permutation, the pathway in the worst-case scenario
involves travelling through at least $\log{_2}{(n!)} \in \Omega(n\log{n})$ by
Stirling's approximation. Although the best case scenario (as seen in insertion
sort) could be $\O(n)$, we cannot assume that every element is sorted
(especially given the claim concerning arbitrary elements). Therefore, I would
argue that the algorithm would fail to sort some orderings given.

Given that I have a black-box implementation of the algorithm, I could try to
prove this argument wrong. In order to test against my argument, I would systematically 
generate every permutation (a la Brute Force sorting) and run it through the
researcher's sorting algorithm. Then, I would check to see if each permutation
was sorted correctly. If every single permutation is sorted correctly assuming
the algorithm runs in $\O(n)$ time, I would request to see the source code
before jumping to any conclusions. Otherwise, I would print the failed ordering
that the algorithm returned. 

Using this code, I would generally expect to see several orderings of the array
to be printed within the output.

### Sources
- https://uwyo.instructure.com/courses/583691/files/folder/slides?preview=79755870 (Slides 59-63)
