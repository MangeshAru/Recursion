# Recursion
Recursion data structure
Recursion --> technique where functions calls itself to solve problem.
key Component -->
1. Base Case --> stops the recursion or prevent infinite loop
2. Recursive Case --> functionns calls itself with smaller input

for example:
factorial using recursion:
int factorial(int n){
if(n==0) return 1;
return n*factorial(n-1);
}

how it works :
factorial(3)
--> 3*factorial(2)
--> 3*2*factorial(1)
--> 3*2*1*factorial(0)
--> 3*2*1*1 = 6

factorial(3) --> factorial(2) --> factorial(1) --> factorial(0) --> base condition


Where Recursion is used 
1. Tree Data structure
2. Graph Algorithm
3. Divide and Conquer Algorithm
4. Dynamic Programing
5. Backtracking
6. Linked List Operation

Cons:
Extra stack memory usage
Risk of stackOverflowError


When to use Recursion:
problem can be broken into multiple identical subproblems
Depth is manageble
Trees/Graph involved


Patterns:
1.Linear Recursion
Functions makes one recursive call.

Template:
void solve(int n){
 if(n==0) return;
 solve(n-1);
}

use cases:
factorial
sum of digits
printing numbers
linked list traversal
---------------------------------------------------------------------------------
2. Tail Recursion
Recursive call is last operation

Template 
int Fact(int n, int ans){
 if(n==0) return ans;
 return Fact(n-1 , ans*n);
}

Use Cases
Factorial
accumalation problems
can be optimized into loop 
-------------------------------------------------------------------------
3. Head Recursion
Recursion call happens before work.

Template
void Print(int n){
 if(n==0) return;
 Print(n-1);
 Sysout(n);
}

Use Cases:
Printing in order
Tree Traversal
----------------------------------------------------------------------------
4. Tree Recursion (Multiple calls)
Each call creates multiple calls.

Templates:
int fib(int n){
 if(n<=1) return n;
 return fib(n-1) + fib(n-2);
}

Use Cases:
Fibonacci
Tree Traversal
Divide And Conquer

Time complexity often exponential
----------------------------------------------------------------------------------------
5. Divide and Conquer
Split->Solve->Combine

Template:
void Solve(int[] arr, int l, int r){
 if(l>=r) return;
 int mid = (l+r) / 2;
 solve(arr,l,mid);
 solve(arr,mid+1,r);
 merge(arr);
}

Use Cases:
Merge Sort
Quick Sort 
Binary Search 
-------------------------------------------------------------------------------------------
6. BackTracking Pattern
Choose --> Explore --> Unchoose

Template:
void backtrack(int idx){
 if(idx == n) return;
 // choose
 backtrack(idx+1);
 //unchoose
}

Use cases:
N-queue
sodoku
permutation
subsets
---------------------------------------------------------------------
7.Subset/Pick-Not Pick Pattern 
At every step --> 2 choice (pick and not pick)

Template:
void subsets(int i , List<Integer> curr){
 if(i==n) {
  print(curr);
  return;
 }
 //pick
 curr.add(arr[i]);
 subsets(i+1,curr);

 //not pick 
 curr.remove(curr.size()-1);
 subsets(i+1, curr);
}

Use cases:
Subsets
Power set 
combination sum

------------------------------------------------------
8. Permutation Pattern
Swap/Mark Visited.

Template:
void permute(int i){
 if(i == n)- return;

 for(int j=i;j<n;j++){
  swap(i,j);
  permute(i+1);
  swap(i,j);
 }
}

Use Cases:
String Permutation
Array permutation
-----------------------------------------------------
9.DFS pattern(Graph/Tree)
Visit--> explore neibhors

Template:
void dfs(Node node){
 if(node == null) return ;
 dfs(node.left);
 dfs(node.right);
}

USe cases:
Tree and Graph Traversal
Connected Component 
----------------------------------------------------------------------

10. Recursion + Memoization(DP)

Store result to avoid recomputation

Template:
int fib(int i, int[] dp){
 if(n<=1) return n;
 if(dp[n] != -1) return dp[n];
 return dp[n] = fib(n-1,dp) + fib(n-2, dp);
}

Use cases:
Fibonacci
knapsack
DP problems


  



















