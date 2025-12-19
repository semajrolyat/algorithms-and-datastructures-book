# 14 - Advanced Topics

A common theme among previous topics is that we can often improve time complexity if we are able to trade more memory than is optimal for more computational efficiency.  The specifics of these strategies vary with the specifics of a data structure's or an algorithm's implementation, but some specific examples are doubling the size of an array when we increase its size to accommodate future appends and storing the answers to Fibonacci as each term is computed.  Here are some potential strategies to optimize time complexity. 

## Amortized Time Complexity

To *amortize* something is "to spread a cost over time" and is a basic principle of accounting.  It's root, *mort-*, is from the latin *mortis* meaning "death" and can be found in words like *mortuary* (processing and storage of the dead), *mortal* (between life and death), and *mortgage* (a lifetime contract).  While the root is more strictly associated with death, it can also more generally be interpreted as meaning lifetime so to amortize means to consider a cost over the lifetime of the object rather than solely to consider the cost at the time it is incurred.

This concept of amortization comes from making large capital investments.  For large investments like buildings and equipment, an initial cost may be extremely large; however, if the investment will not need further large investments over a long time, any annual maintenance costs are relatively small, and is functionally critical to a valuable system, then while the cost of the investment is sunk at a single time, the overall cost can be instead considered to be spread out over the lifetime of the investment up until it is replaced.  For example, a company may need a factory to generate its product and while the cost of the factory is a massive initial investment, it will "pay for itself" over time because the factory will continue to produce products for years and years without the need for another massive investment.  It will require additional maintenance and occasional significant repair as well as resource inputs but if the business plan is sound the factory may produce product over time that eventually will cover all total lifetime costs including initial investment, interests, and maintenance as well as producing profits.  Once again, we can look to this other discipline and set of concepts and leverage the same principle with our data structures to improve time complexity.

In our domain, an array can be a costly investment in terms of computation time if it is adhering to any policy that expects the array to dynamically grow.  We have to be very considerate about how we grow an array because every time the array needs to be increased in size, we incur an $O(n)$ cost.  We can think about the array in the same way as our factory above where the array is an investment with a large computational cost for increasing its size.  We have established that the most basic strategy to appending to a full array with a dynamic growth policy is the allocate a new array with one additional space of capacity at a cost of $O(?)$, copy all elements from the old array into the new array at $O(n)$, and assign the element at the largest index in the new array to the element to insert at $O(1)$ for a total of $O(n)$ assuming $O(?) < O(n)$.  This means that growing the array by one element each time is linear time complexity in its best, average, and worst cases.  While we cannot prevent the worst case from arising, if can we delay the allocation we might amortize that linear time complexity cost for the array allocation over multiple append calls enabling the program to make a number of calls to a constant time append with an highly infrequent call to a linear time append.  This seems like a winning idea, but there is an open question about how much space should we allocate.   

From a space perspective, we have a lot of memory in a modern system, so why not trade some of space for improved time efficiency.  However, we don't want to aggressively reserve space we are unlikely to need as we generally need to keep memory free and available for other usage so there is some balance we need to find between the frequency of the allocation and the size of the space reserved.  Given that, it is reasonable to assume that if a set is growing and we need to store $n$ elements, it is likely that we will need to store $n$ more elements as the process continues.  In other words, when appending a new element to the array requires increasing the size of the array, instead of allocating an array of size $n+1$, we allocate an array of size $2n$.  Allocating the new array will still cost $O(n)$ because we will need to traverse and copy $n$ elements from the source array; however, this will also buy at least $n$ further append operations at a cost of $O(1)$ before incurring another $O(n)$ allocation event.  This means that when using the doubling strategy to grow an array in response to an append operation, the array's worst case time complexity is linear, $O(n)$, but its amortized time complexity (time complexity over time) is constant time, $O(1)$ which is also its average time complexity.

## Dynamic Programming

Dynamic Programming is a programming technique where one or more solutions to a previous problem act as input to solve subsequent problems.  It is a self-referential technique and therefore naturally fits with recursive implementations.

The optimization behind dynamic programming is not a surprise.  Just as with other strategies, we are generally exchanging space (store previous solutions) for time (to compute the $n+1$ solution).  The key is to store any solutions after they are computed in a structure.  By storing the computed solutions in a structure with fast retrieval, the solutions become available as input into the algorithm and the data from our stored solutions can be used to improve the efficiency of computing the next solution by reusing the previously computed value instead of recomputing it.

Because it is built on both inductive principles and recursion, it can be difficult to initially conceive.  We will look back at two problems, Fibonacci Sequence and the Manhattan Problem, which can easily be converted into dynamic programming problems.  By using dynamic programming, we will reduce their time complexities from an intractable non-polynomial time to a very reasonable polynomial time.

### Fibonacci

From Chapter 4, recall the Fibonacci Sequence:
$$
f(x)=\begin{cases}       0 & x = 0 \\      1 & x = 1 \\      f(x-1) + f(x-2) & x > 1    \end{cases}
$$
We found that the above can be implemented using the following pseudocode: 

```pseudocode
fibonacci(x) → integer >= 0 where x is an integer and x is >= 0 :
	if x = 0 : 
		return 0
    if x = 1 : 
		return 1

	return fibonacci(x-1) + fibonacci(x-2)
```

However, this implementation has exponential $O(2^{n})$ time complexity and linear $O(n)$ space complexity.  The time complexity arises because we make two subsequent recursive calls to this function for every non-base case call to the function.  The space complexity arises because we generate a function call tree on the stack to solve the problem and the maximum depth of the tree is $n$ where $n$ is literally the input value we are calling $x$ in the examples above.

While we know there is an iterative approach, consider if we can leverage recursive principles to improve the algorithm without using recursion itself.  In other words, can the recursive function be rewritten so that it solves the problem without calling itself.  You might ask how is it then recursive if it does not call itself.  The twist is that we will sill use the recursive formula but we will store the solutions as we calculate them.  The conventional recursive algorithm uses $O(n)$ space anyway, so if our algorithm uses an array with equivalent space, it is no more resource demanding than the conventional algorithm.   

Consider the following implementation of Fibonacci:

```pseudocode
fibonacci(x) :
	int[] A = new int[x+1];
	A[0] = 0;
	A[1] = 1;
	for(int i = 2; i <= x; i++) {
		A[i] = A[i-1] + A[i-2]    // The dynamic programming step
	} 
	return A[x]
```

In this version, the solutions are stored in an array.  This array is initialized with the base case(s) and then the program iterates on the dynamic programming problem until the solution is calculated.  The solution is stored in the last element of the array and this element is returned.   

The arguments that the time complexity of this algorithm is no better than the original iterative technique and the original iterative technique uses constant space suggest that this algorithm has no place; however, if you needed to calculate an entire Fibonacci sequence up to $x$, this algorithm could do so with simple changes at no additional computational cost, so not only does this algorithm solve for a single Fibonacci number but it is also able to compute (and could return) the entire Fibonacci sequence up to the input value. 

### Manhattan

Recall the Manhattan Problem from Chapter 4:

<img src="/home/jrt/gwu/course/cs1112/assets/manhattan.png" style="zoom:30%;" />

We arrived at the following recursive implementation:

```pseudocode
manhattan(row, col) → paths from this row and col :
	if row = 0  :
		return 1
    if col = 0  :
    	return 1
    	
    count = manhattan( row - 1, col )
    count += manhattan( row, col - 1 )
    return count 
```

While we did not perform a rigorous time complexity analysis, we were able to approximate that it is at best exponential, $O(2^{n})$, because it has the same basic structure as the Fibonacci recursive implementation; however, this problem is actually worse than an exponential because it is a combinatoric,  proof of which is left for another course.  Regardless, the algorithm is intractable for large inputs in its current form, so can we apply dynamic programming to the problem and solve it more efficiently and the answer is yes.  

Like many optimization strategies, we will exchange a portion of free space for faster processing time.  In reality, the original Manhattan algorithm still used memory to hold intermediate calculations, however, it did so on stack so the spatial complexity was not immediately apparent.  This algorithm will still cost more in terms of memory than the original Manhattan algorithm, but this algorithm will use the space to leverage the recursive properties of the problem without having to use recursion itself and will run with a significantly more efficient time complexity than the algorithm above.   

We will use a multidimensional array to hold the intermediate solutions.  This array must have the same dimensionality as the grid above.  Note that there are four streets in the vertical dimension and there are six streets in the horizontal dimension.  The cells of the array will contain the calculated solution for the number of paths from the intersection the cell maps to on the grid.  In Java, conveniently every value in an integer array will initialize to zero, so the initial state of the array is benign and it is ready to work with once the array is allocated.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_setup.png" style="zoom:20%;" />

The base condition information needs to encoded into the array in the second step.  Here we assign any cell on the zero row or the zero column a value of 1.  This reflects that when the right edge is reached or the bottom edge is reached, there will be only one path to follow to the solution.  Note that we will ignore the value in cell [0,0] hence the reason it remains set to the value 0.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_basecases.png" style="zoom:20%;" />

Consider the implication of this code from the above implementation:

```java
	count = manhattan( row - 1, col )
    count += manhattan( row, col - 1 )
```

The code says the solution to $A[i,j]$  where $A$ is the multidimensional solution array is:

$A[i,j] = A[i-1,j]+A[i,j-1]$

or in other words, the solution to the current problem is equal to the sum of the solution to the problem from the same column/previous row and the solution to the problem from the same row/previous column.  

| <img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_process.png" style="zoom:20%;" /> | <img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_process2.png" style="zoom:20%;" /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| A[1,1] is equal to the sum of A[1,0] + A[0,1]                |                                                              |

Once the base cases have been computed, we can compute an entire column quickly by iterating over the column and summing according to the above formula.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_1st row.png" style="zoom:20%;" />

This allows us to create a nested loop that will iterate over every cell of the array and compute the solution.

<img src="/home/jrt/gwu-new/course/cs1112/assets/manhattan_dp_solution.png" style="zoom:20%;" />

Now our algorithm is capable of computing, retaining, and even returning the entire solution.  The recursive algorithm illustrated above was non-polynomial with at best an exponential time complexity.  This implementation is simply a nested `for` loop; however, we need to consider the dimensionality of the problem with respect to the input so that we summarize the efficiency correctly.

Because  a nested `for` loop is involved, it is tempting to just claim quadratic time complexity and call it a day; however, this would be incorrect.  The input measure can be reduced from two dimensions to one dimension if we realize that the size of the input is the number of intersections in the grid which has a clear, easily expressible relationship with the number of rows and the number of columns:

​	$intersections = width \times height$

Therefore our analysis variable is just $n$ where $n$ is the number of intersections, so the time complexity of the dynamic programming approach is linear.

```java
public class ManhattanDP {

    static int[][] A;

    public static void main(String[] argv) {
        int height = 5; 
        int width = 3;

        A = new int[height+1][width+1];

        // initialize base cases along edges
        for(int i = 1; i <= height; i++) {
            A[i][0] = 1;
        }
        for(int i = 1; i <= width; i++) {
            A[0][i] = 1;
        }

        // dynamic progrmming approach notes that the total number of
        // paths at any given intersection is the sum of the downward 
        // paths and the rightward paths
        for(int i = 1; i <= height; i++) {
            for(int j = 1; j <= width; j++) {
                A[i][j] = A[i-1][j] + A[i][j-1];
            }
        }

        String msg = "For a " + width + " x " + height + " manhattan grid,";
        msg += " there are " + A[height][width] + " shortest paths.";

        System.out.println(msg);
    }
}
```







## n-ary Tree

Point Cloud, Quadtree/Octree

## Priority Queue

Queue of queues or more accurately an array of queues.  Each queue has a **priority** property, typically an int in range of [0,MAX_PRIORITY].


