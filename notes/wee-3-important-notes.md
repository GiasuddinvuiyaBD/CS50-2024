## CS50 Week-3 Important Note

**Topics:**

1. How can we compare algorithms with `O` and omega notation? 

2. What are **structs**?

3. How can we make user of **recursion**?


**Algorithm:**
An algorithm is simply  a set of steps to complete some task. 


- Searching
    - linear search
    - binary search
- Sorting 

**Notes:**
- Binary search `log2(7)` it means log devided 2 to 7. it can take 3 steps or it could be `log2(n)`

- linear search `7`. it can take 7 steps for finding last val or it could be `n`


For leargest number of data's

- O(n) linear
- O(log(n)) binary

for linear search and binary search the best case it only take 1 step. For this omega notation comes in.

Omega notation says, given any kind of input would be the fewest number of steps we would ever take


**Common Notations:**
- O(1)
- O(log(N))
- O(n)
- O(n^2)

**Omega**
- omega(1)
- omega(log(N))
- omega(n)
- omega(n^2)

**Sorting Algorithm**

- Merge sort 
O(Nlog(N))
omega(Nlog(N))

- Selection Sort
O(N^2)
omega(N^2)

- Bubble Sort
O(N^2)
omega(N)


**Structs**

A structure is great. We want to create our very own data type to use in our program.

It's not quite a full data type, but it is  a way encapsulate information so we can refer to it with only one name.

Example: 
```c
    typedef struct
    {
        string name;
        int votes;
    }
    condidate;

    /*
        Create a new "type" which holds a collection of other basic types.

        others
        _______
        Give the struct a name that can be re-used in the rest of the file.

        known as a structures
        members.
    */

candidate president;
president.name = "Samia";
president.vote = 10;

// here i can create my very own array 

candidate candidaates[4]; 

```
**Most Votes**
- create an array of candidates.
- search the array to find the most votes aways to any single candidate.
- Print out that candidates name.


```c
#include <cs50.h>
#include <stdio.h>
typedef struct
{
    string name;
    int votes;
}
condidate;

int main(void)
{
    const int num_candidates = 3;
    condidate candidates[num_candidates]; 

    candidates[0].name = "Carter";
    candidates[0].votes = 10;

     candidates[1].name = "Yullia";
    candidates[1].votes = 32;

     candidates[2].name = "Gias uddin vuiya";
    candidates[2].votes = 100;

    // TODO: Find highest number of votes
    int highest_votes = 0; 

    for (int i = 0; i < num_candidates; i++)
    {
        if(candidates[i].votes > highest_votes)
        {
            highest_votes = candidates[i].votes ;
        }
    }

    printf("%i\n", highest_votes);

    // TODO: Print name of candidate with highest number of candidate.

    for(int i = 0; i < num_candidates; i++)
    {
        if(highest_votes == candidates[i].votes)
        {
            printf("%s\n", candidates[i].name);
            return 0;
        }
    }

}

// note you ginerally don't want to repeat code in your program.

```

**Recursion**
So often, recursion tends to be a very elegant solution to some problems. and for that reason, we have to try to find a way to use recursion to solve problems. The caveat here is that it's not always the best way to do things but it can be elegant in certain cases. And so we'll talk about the kinds of problems. that actually have good potential to be solved with recursion.

Now, one problem like this, this idea of a factorial. 


a factorial is simplly a number where you take that number and multiply it by the number that's 1 less than it, then the number that's 1 less than that, the number that's 1 less than that,

`So let's take a look at an Example here.`

`
1! = 1
2! = 2 * 1
3! = 3 * 2 * 1
4! = 4 * 3 * 2 * 1
`

fact(1) = 1
fact(2) = 2 * fact(1)
fact(3) = 3 * fact(2)
fact(4) = 4 * fact(3)
fact(5) = 5 * fact(4)

So what makes this problem good for a recursive solution?

What do you notice in particular about now 2 factorial?

Seems like to me that the solution for 1 factorial


**solve the factorial number problem.**

```c
    int fact(int n)
    {
        // base case
        if (n == 1)
        {
            return 1;
        }
        else
        {
            return n * fact(n - 1);
        }
        // recursive case

        // more readable code

    if (n == 1)
    
        return 1;
    else
        return n * (fact - n);

    
    }
```

- In general, but not always, recursive function replace loops in non-recursive function.

```c
int fact(int n)
{
    if (n == 1)
    
        return 1;
    else
        return fact(n - 1);
}

//  using loop for solving this problem 

int fact2(int n)
{
    int product = 1;
    while(n > 0)
    {
        product *= n
        n--;
    }
    return product;
}
```

**Challenge**
```c
int collatz(n)
{
    if (n == 1)
    {
        return 1;
    }
    else if (n % 2 == 0)
    {
        return collatz(n / 2);
    }
    else if (n % 2 == 1)
    {
        return collatz(3 * n + 1);
    }
}

// right answer is here
int collatz(n)
{
    if (n == 1)
        return 0;
    else if ((n % 2) == 0)
        return 1 + collatz(n / 2);
    else 
        return 1 + collatz(3*n + 1);
}
```



