#seq2struc

##Introduction

Suppose you have a list of staples, and a very long scaffold. Can you extract the secondary structure from purely sequence information? 

Let's phrase this slightly more carefully.  

There exists a known set of staples which physically correspond to oligonucleotides, and which are represented by strings of characters from the alphabet {a,t,g,c}. 

We want to minimize crossovers, and maximize sequence assignment.

Not guarantted to be a complete mapping! Some spare scaffold / staple.

Not trivial problem.

Seems pairwise but isn't.

Underdetermined type 1

--------TT---------->
--------A
        |
--------A
<-------T------------

--------TT---------->
--------AA
         |
--------
<-------T------------

etc. In principle can be determined only with trivial secondary structure knowledge.

Underdetermined type 2

--------TT---------->
--------AA----------
        || 
--------AA----------
<-------TT----------

--------TT---------->
--------AA----------
        //
       //
--------AA----------
<-------TT----------

Due to possible compensation, cannot be determined from secondary structure without some appeal to geometry of embedding. Can be determined through graph traversal.

##Algorithm

Take a random staple. Find the longest substring in the sample present in the scaffold via a suffix tree. Remove the center of the substring (just a bit, not sure much now) from the staple. Then find the longest substring of the modified staple in the scaffold. Repeat until there is no unassigned nucleotide #are we sure?.

Possible doubly assigned nucleotides? But this is what we want!

Use double assigned nucleotides to get a SET of possible assignment for that staple. Repeat for every staple, such that for every staple there is a set of possible assignments.

We now need to find out through mutual consistency which staple locations are actually valid. Underdetermined type 1 can be determined through use of an SAT solver, with the requirement that scaffold nts have at most one staple nt assigned. // problem with maximizing?

Underdetermined type 2 can be solved through an additional Boolean satisfiability step. The criterion necessary for determining uses a graph representation of the connectivity.

--------------------------------------->
---------<-------d-------->-------------
        ||                || 
-----------------x----------------------
<---------------------------------------

d must be an integer multiple of 10.5. We are not certain to get something this nice however... But there is probably some requirement of the minimum loop that can be effectively phrased as a Boolean clause. I'm going to have to sketch it to get a better idea...

##Implementation

##Example
