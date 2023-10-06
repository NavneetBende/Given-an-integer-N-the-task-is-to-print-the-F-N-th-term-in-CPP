# Given-an-integer-N-the-task-is-to-print-the-F-N-th-term-in-CPP

Print F(N)th term in C++
 

Here, in this page we will discuss the program to print the F(N)th term in C++ Programming Language.  A function f is defined as follows F(N)= (1) +(2*3) + (4*5*6) … N. We are given with an integer N and we need to print the F(N)th term.

Example :

Input : 4
Output : 5167
Explanation : 1 + (2*3) + (4*5*6) + (7*8*9*10) = 5167.
Print F(N)th term in C++
Method 1 (Using Recursion) :
Create a recursive function say term(int calculated, int current, int N)
Declare a variable cur to hold the product of the terms and initialize it with 1.
Base condition will be if(current == N+1) then, return 0. Here, current denotes the current term of the series.
Now, run a loop to calculate the product of terms till current.
Set i= calculate. Termination condition of the loop will be i>= calculated + current.
Inside loop set cur *= i
After execution of loop return cur + term(i, current+1, N)
print f(n)th term
Code to Print F(N)th term in C++
Run
#include<bits/stdc++.h>
using namespace std;

// Recursive function 
int term(int calculated, int current, int N) 
{
    int i, cur = 1;

    // Base Condition
    if (current == N + 1) 
       return 0;

    // product of terms till current
    for (i = calculated; i < calculated + current; i++)
        cur *= i;

     return cur + term(i, current + 1, N); 
}

// Driver Code
int main()
{
    int N = 3;

    cout<<term(1, 1, N);

    return 0;
}
Output :

127
Method 2 (Using Loop) :
Create a function say term(int calculated, int current, int N) to calculate the required N-th term.
Declare a variable result = 0.
Run a while loop till current != N+1.
Inside while loop declare a variable cur to hold the product of the terms and initialize it with 1.
Now, run a loop to calculate the product of terms till current.
Set i= calculate. Termination condition of the loop will be i>= calculated + current.
Inside for loop set cur *= i.
After execution of for loop set calculated = i, result += curr and increment current value by 1.
After the execution of while loop return result.
Code to Print F(N)th term in C++
Run
#include<bits/stdc++.h>
using namespace std;

//Function to calculate N-th term
int term(int calculated, int current, int N) 
{
  int i, result = 0;

  while(current != N + 1){ 

    int cur = 1;
    // product of terms till current
    for (i = calculated; i < calculated + current; i++)
       cur *= i; 

    calculated=i;
    result += cur;
    current++;
  }
   
   return result; 
}

// Driver Code
int main()
{
  int N = 3;

  cout<<term(1, 1, N);

  return 0;
}
Output :

127
