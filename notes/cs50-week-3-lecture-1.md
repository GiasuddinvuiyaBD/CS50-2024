## CS50 Week-3. Lecture-1 Algorithm


**Algorithms**

**topic: searching**
- liner search (left to right) or from right to left.

- Devide and conquer.
If you search for a contact using autocomplete. It is so called
that's finding people in your address book.It's not starting top to bottom or bottom up. It's probably going roughly to the middle and then doing the top half or the bottom half, repeating again and again.

note : An array is important in C because, it's a list of values or collection of values but the real key distinction in an array in C is that it's **contiguous.** The bytes are back to back to back somewhere in the computer's memory.

At least for any given data type, be it an int, a float a bigger string.


<!-- Psudecode linear search -->

> For each door from left to right
        if 50 is behind door
            return true
    Return false;
this is wrong

> For i from 0 to n-1
    if 50 is behind doors[i]
        return true
   Rturn false

<!--  devide and conqer approach -->
**binary search**
>   If no doors left
         return flase
    If 50 is behind middle door
        return true
    Else if 50 < middle door
        search left half
    Else if 50 > middle door
        search right half

**more technical:**
> if no doors left
        Return false
  if 50 is behind doors[middle]
        return true
  Else if 50 < doors[middle]
        search doors[0] through doors[middle - 1]
  Else if 50 > doors[middle]
        search doors[middle + 1] through doors[n-1]
   
==Note: Practice it on you own==

any questions Linear or binary search.



## BIG O
**Big O is use for running time complexity.**

- **O(n^2)** `quadratic time algorithm.`   it's the double of `O(n)`.
- **O(n log n)** `This is n log n` 
- **O(n)** `linear time algorithm.`  big of of n, so to speak means that it takes linear time, in other words 1,2,3,4 etc.
- **O(log n)** `logarithmic time algorithm.`
- **O(1)** `constant time algorithm.` This describe something taking just one step total or a constant number of steps total.

The mathmetical formola as i write above describe as a function of the size of that input. how fast or slow the algorithm's going to be.

So, BIG O represents an upper bound the number of steps that you might be counting and we often use it to consider the worst case and the worst case, John Harvard, or whoever might be all the way at the end of the phone.

## Binary search O(log n)
The worst case of binary search is O(n) but sometimes can you can lucky can get your expected result at first index of the array or second index but also you can get your result at the end of the indexes so that's why the worst case of binary search O(n);


But sometime you get lucky and find it quicker so, we don't always want to talk about things in terms of an upper bound, like how many steps in the worst case might this algorithm take. Sometimes it's useful to know in the best case. How few stpes might an algorithm take.


**So for that, we have this capital Greek Omega, which which is another symbol in computer science and `whereas big O represents upper bound,omega represents lower bound`**

## Theta notation
Whereby if big o and omega happen to be the same, which is not always the case but can be, then you can say that **algorithm is in theta** of such and such


**`Note: Big O Upper or west case bounce Omega lower bounce best case and theta will represent when both can be`**

## Now jumb into the code. 

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int numbers[] = {20,500,78,3,8};

    int n = get_int("Number: "); 

    for(int i = 0; i < 7; i++)
    {
        if(numbers[i] == n)
        {
            printf("Found\n");
            return 0; // it will exist  the fun
        }
    }
    printf("Not found\n");
    return 1; // it will exist the fun
}

// Note : when you want your main function to end prematurely if so, you can litarally just return the value and even though this feels a little backwards, this is just the way it is. you return zero to indicate success. And you return any other integer to indicate failure.

// So by convention, people go to 1 and then 2 and then 3. 

```

**Now we are gonna practice it with string**

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string stringts[] = {"battleship", "boot","cannon","iron","thimble","top hat"}; 

    string s = get_string("String : "); 

    for(int i = 0; i < 7; i++)
    {
        if(stringts[i] == s)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}

/*
Note: Here it won't work. it will work for integer but not string.


For string we have another libary

string 
1. strlen
2. strcmp for string comparison.

this two func come form string libary.
*/ 
#include <cs50.h>
#include <string.h>
#include <stdio.h>


int main(void)
{
    string stringts[] = {"battleship", "boot","cannon","iron","thimble","top hat"}; 

    string s = get_string("String : "); 

    for(int i = 0; i < 7; i++)
    {
        if(strcmp(stringts[i], s) == 0)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}

```

**Now we are going to see another example of strings**

```c
#include <cs50.h>
#include <string.h>
#include <stdio.h>

int main(void)
{
    string user_name[] = {"Carter", "David", "John"}; 
    string numbers[] = {"+1-729-435-1000","+1-909-435-1450","+1-686-907-1090","+1-729-435-8976"};

    string name = get_string("Name : ");

    for(int i = 0; i < 3; i++)
    {
        if(strcmp(user_name[i], name) == 0)
        {
            printf("Found %s\n", numbers[i]);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```

## Data structure. 

Create your own data structures, your own types of variables, largely using syntax we've seen thus far. So to do this, let me propose that in order to represent in a phone book. 

So, can we create a data structure where can you store multiple types of data.


-- So a structure can ba a variable that contains any number of other variables,

```c
typedef struct
{
    string name;
    string number;
}
person;

// this is will create a new data type in c called person

int main(void)
{
    person people[3];

    people[0].name = "carter";
    people[0].number = "+1-617-496-1000";

    people[1].name = "David";
    people[1].number = "+1-892-902-1030";

    people[2].name = "John";
    people[2].number = "+1-903-832-833";

    string name = get_string("Name : ");

    for(int i = 0; i < 3; i++)
    {
        if(strcmp(people[i].name, name) == 0)
        {
            printf("Found %s\n", people[i].number);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}

/*
   1. typedef means the name of the data like person
    2. struct means
        {
            string name;
            string number;
        }
*/

```

## Sorting algorithm

1. Selection sort O(n^2);

***pseudo code.***

for i from 0 to n-1
    Find smallest number between numbers[i] and numbers[n-1]
    Swap smallest number with numbers[i]

Note: resource for sorting algorithm



2. Selection sort. 

***pseudo code.***
Repeat n times
    For i from 0 to n-1
        If(numbers[i] and numbers[i+1]) out of order
            swap them
        If no swaps
            Quit



<!-- working like this -->
(n-1)*(n-1)
n^2-1n-1n+1
n^2-2n+1

O(n^2)

<!-- best case -->
O(n) bubble sort

## Recursion
In programming and in mathematics, there's this idea of recursion. A recursion is a description for a function that calls itself. A function that calls itself is recursive.

<!-- here is the pseudo code of binary search erliar -->

If no doors left
    return flase
If number behind middle door
    return true
Else if number < middle door
    Search left half
Else if number > middle door
    search right half


***What's happening to the size of the problem for each of these lines?***


**Piramyds code**
```c
#include <cs50.h>
#include <stdio.h>

void draw(int n);

int main(void)
{
    int height = get_int("Height: ");
    draw(height);
}

void draw(int n)
{
    for(int i = 0; i < n; i++)
    {
        for(int j = 0; j < i + 1; j++)
        {
            printf("#");
        }
        printf("\n");
    }
}

// recursive solution
void draw(int n)
{
    // if nothing to draw
    if(n <= 0)
    {
        return ;
    }
    // print pyramid of height n-1
    draw(n - 1); 

    for(int i = 0; i < n; i++)
    {
        printf("#");
    }
    printf("\n");
}


```

<!-- google search recursion -->


## merge sort

**Pseudo code of merge sort**

If only one number 
    Quit
Else
    Sort left half of numbers
    sort right half of numbers
    merge sorted halves







