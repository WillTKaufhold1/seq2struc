#seq2struc

##Introduction

Suppose you have a list of staples, and a very long scaffold. Can you extract the secondary structure from purely sequence information?

Let's phrase this slightly more carefully.  

The staples are a set of strings constructed from the alphabet {A,T,G,C}. The scaffold is a single string, also constructed from {A,T,G,C}. The reverse complement of the scaffold is the reversed string, with A substituted for T, T substiuted for A, G for C, and C for G. 

A secondary structure is an assignment of nucleotides from the staples to nucleotides on the scaffold. Each nucleotide on the staples may bind at most one nucleotide on the scaffold. An assignment is only valid if staple characters of identity T are mapped to scaffold characters of identity A, and so forth.

A secondary structure is said to contain a crossover if contiguous nucleotides in a particular staple string are not mapped to contiguous nucleotides in the scaffold string. That is to say that #directionaltiy?

##Algorithm



##Implementation

##Example
