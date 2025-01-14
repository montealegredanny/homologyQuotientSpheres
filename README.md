# homologyQuotientSpheres
Given a subgroup G of the symmetric group S_n compute the homology of S^(n-2) / G.  This is the code used in the paper "Moduli spaces of tropical curves are simply connected" with Daniel Allcock and Sam Payne, in preparation. 

The group G should be stored in a file group_file. Each line of group_file should be a space separated list of the numbers 0, 1, ... n-1 representing a generator for G < S_n. For example, the file for S_4 could look like:

1 2 3 0

1 0 2 3

To compute H_* (S^(n-2)/G, Z), run:

python3 computeHomologyFromGroup.py group_file output_dir n

where group_file is as above, output_dir is a directory to store the data generated by the program (the barycentric subdivision of Delta^n, the matrices of C(S^(n-2)/G), Z ), and the elementary divisor data). The output to the terminal will look like:

1 rank [elementary divisors]

2 rank [elementary divisors]

...

n-2 rank [elementary divisors]

where for each line, the integer k on the left indicates the homology group H_k, rank is the rank of H_k, and [elementary divisors] is a list of the elementary divisors of H_k. 


To verify the results in the proof of Theorem 1.3 in the paper, one could run, e.g., 

python3 computeHomologyFromGroup.py symSquarePyramid.gp squarePyramid 8

and get

1 0 []

2 0 []

3 0 []

4 0 [4]

5 0 [2]

6 0 []

as the output. The group data for the other two are stored in symTriangularPrism.gp and symK33.gp. 
