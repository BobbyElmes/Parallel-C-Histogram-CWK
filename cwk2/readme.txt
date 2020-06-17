Complete the table below with your results, and then provide your interpretation at the end.

Note that:

- In the table below, the word "node" refers to cluster nodes - in DEC-10, one node coresponds
  to a single desktop machine.

- See Lecture 8 and the start of Worksheet 2 for instructions on how to launch an MPI program on
  more than one node, with a specified number of processes on each node.

- When calculating the parallel speed-up S, use the time output by the code, which corresponds
  to the parallel calculation and does not include reading in the file or performing the serial check.

- Take as the serial execution time the time output by the code when run with a single process
  (hence the speed-up for 1 process must be 1.0, as already filled in the table).

- If you used a different input.txt to test your code, ensure you restore the original input.txt for
  the timing runs.


No. Process:                        Mean time (average of 3 runs (4dp))           Parallel speed-up, S:
===========                         ============================:           ====================
1                                              0.0114                                1.0
2 (same node)                       	       0.0066				     2.2
4 (same node)                       	       0.0041				     2.8
4 (2 nodes, 2 per node)             	       0.1709				     0.067
8 (2 nodes, 4 per node)             	       0.1705				     0.067	
12 (3 nodes, 4 per node)            	       0.2237				     0.051


Architecture that the timing runs were performed on (normally DEC-10):DEC 10


A brief interpretation of these results (2-3 sentences should be enough): We can see that the parallel code ran significantly faster than the serial code when the processes 
were all run on the same node. The more processes per node the faster it ran, showing that splitting the text into sub texts, evaluating and adding them back together in a binary 
tree works very well. However, when multiple nodes are used a much larger overhead for communication is added, causing the parallel code to run significantly slower than the serial code.





