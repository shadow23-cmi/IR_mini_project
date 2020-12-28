# IR_mini_project
## Modified Front Coding with variable Blocking factor
### Abstract
We know the importance of text compression in Information Retrieval. We are
dealing with huge databases and thus the more space we save, the better. While
front coding, there can be many instances where we can save space just by
having a variable block length. In this project we aim to attain a better
compression algorithm while front coding using the idea of variable block length.
### Introduction
Dictionary as a string instead of a dictionary as an array is one of many ways to
improve the space complexity of postings list. We can exploit the fact that
consecutive entries in an alphabetically sorted list share common prefixes, for
example, the word list [active, actively, activities] has the common prefix ‘active’.
This observation leads to the idea of front coding. In front coding with blocking
factor, k=4 we get 6a*ctive7◊ctively9◊ctivities6◊lgebra for the word list [active,
actively, activities, algebra]. It can be seen that in this case, the front coding with
blocking factor k = 4 is not optimal. So instead of taking k as constant, if we vary
k according to consecutive words with longest common prefixes, then better
compression is achieved. For example, if we split the block in two parts, with k=3
and k=1, we get, 6activ*e3◊ely5◊ities 6algebra. So, we can see that more than
10 bytes of space is being saved by doing the above modification.
More Examples:
1) Front coding with constant blocking factor k=8
9i* nfection5◊nform10◊nformation7◊nformed5◊nfuse10◊nstitution4◊ssue5◊ssues
Front coding with variable blocking factors k=1,3,2,2 respectively
9infection 5inform*5◊ation2◊ed 6in*fuse9◊stitution 5issue*1◊s
The variable blocking factor saves more than 10 bytes of space.
2) Front Coding with constant blocking factor k=4
5extra*2◊ct6◊ctable5◊ction 9extra*ctor4◊dite6◊dition6◊polate
Front coding with variable blocking factors k=8
5extra*2◊ct6◊ctable5◊ction4◊ctor4◊dite6◊dition6◊polate
The variable blocking factor saves 5 bytes of space.
