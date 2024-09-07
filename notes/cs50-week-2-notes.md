# CS50 Week-2 Notes. 

## There are four things work under the hood of programming

1. Preprocessing
2. compiling
3. assembling
4. linking


```c
#include <cs50.h>
#include <stdio.h>


int main(void)
{
    string name = get_string("What's your name ?");

    printf("hello, %s\n", name);
}

```



**What is probably inside of cs50.h ?**

**ans: just a prototype of the string. Where we copy and past the string file**

> The preprocessor step, step 1 of 4, just does that find and replace, if you will.   So, preprocessing converts all of those hash includes lines to whatever the underlying protoypes are. 

## Week 2: Notes
**Topics covered :**
- Welcome!
- Compiling
- Debugging
- Arrays
- Strings
- String Length
- Command-Line Arguments
- Exit Status
- Cryptography
- Summing Up

**Link :**
[Notes](https://cs50.harvard.edu/x/2024/notes/2/)


## Video Notes

**Video's topic:**
- Compiling
- Arrays
- Strings
- String Length
- Command-Line Arguments
- problem-set 2



```c
    // this fun will show an error becuase we didn't include <stdio.h> or standart library


    int main(void)
    {
        printf("Hello")
    }
```


## Arrays
This is a way of storing data in a computers memory. 


if we want to create an array, C needs to know three things about that array. 

1. name of the array
2. size of the array
3. what type of data we will store inside the array. 

**Example :**

`int nights[5];`

Now store the value inside the array. 

```c
    int nights[5] = {7,8,6,7,8};
```

**Write a program that double all the element of the array.**

```c
    #include <cs50.h>
    #include <stdio.h>

    int main(void)
    {
        // better way 
        int size = get_int("Enter a size: ");
        int array [size];
        int sequence[5];
        squence[0] = 2;
        printf("%i\n", squence[0]);

        // we are going to perfrom an for loop for dubling the squence

        for(int = 1; i < 5; i++)
        {
            sequence[i] = sequence[i - 1] * 2;
            printf("%i\n",sequence[i]);
        }

        // perfrom another loop 
        for(int = 1; i < size; i++)
        {
            sequence[i] = sequence[i - 1] * 2;
            printf("%i\n",sequence[i]);
        }
    }

```

## String
**Character A = ASSCI 65**;
**Character a = ASSCI 90**;

**Alphabetical:**
- Write a program to check if an array of characters is in alphabetical order.
- Assume the characters are all uppercase
```c
    #include <cs50.h>
    #include <stdio.h>
    #include <string.h>

    int main(void)
    {
        string phrase = get_string("Enter a phase: ");
        int length = strlen(phrase);

        for (int i = 0; i < length; i++)
        {
            // i want to see every single charactor
            printf("%c", phrase[i]);
        }
        printf("\n")

        // if we want to take ascci value form string 
        for (int i = 0; i < length; i++)
        {
            // assci value
            printf("%i ", phrase[i]);
        }

       // check if characters are not alphabetical order
        for (int i = 0; i < length - 1; i++)
        {
            if(phrase[i] > phrase[i + 1])
            {
                printf("Not in alphabetical order\n");
                return 0;
            }
            else
            {
                printf("Alphabetical order\n");
                return 0;
            }
        }
        printf("This are alphabetical order\n");
    }
```


## Command-line Arguments.

- When we write the command **make hello**, Now i am giving make some input or some argument, telling it it to made. I'm telling it here to make the program hello. and also we can do the same thing for **check50**


#### Example: 
`./mario`

```c
// this fun doesn't take any argument, void
    int main(void)
    {
        int height = get_in("H: ");
    }

    // without void, this fun takes two arguements
    int main(int argc, string argv[])
    {

    }
    // here is two different things int argc and string argv with some braces.
```

**argv**
- write a program that prints each command-line argument given to the program.

**argv.c**
```c
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
    for(int i = 0; i < arvc; i++)
    {
        printf("argv[%i] is %s\n", argv[i]);
    }
}
```

**mario.c**
```c
#include <cs50.h>
#include <stdio.h>
#include <stdlib.h>

int main(int argc, string argv[])
{
    if(argc != 2)
    {
        printf("./mario number\n");
        return 1;
    }
    int height = atoi(argv[1])
}

// note: atoi convert string to integer value and it's come from <stdlib.h>

```

**What question do we have on argc and argv?**

The summary of what argc and argv are. In a single sentence argc is the number of inputs to our program at the command line.

On the other hand a single sentence argv is the array of strings, the array of inputs to our program at the command line.


##  Short Video.

**Functions:**

- Function declarations
    `return-type name(argument-list)`
- The **`return-type`** is what kind of variable the function will output.
- The **`name`** is what you want to call your function. 
- The **`argument-list`** is the comma-seperated set of inputs to your function, each of which has a type and a name.


**Example:**
`int add_two_ints(int a, int b);`
**write up a function to multiply two floating point numbers.**
```c
    #include <cs50.h>
    #include <stdio.h>
    int mult_two_reals(float num1, float num2);

    int main(void)
    {
        int multiplied = mult_two_reals(30.2, 54.3);
        printf("%f\n", multiplied);
    }

    float mult_two_reals(float num1, float num2)
    {
        return num1 * num2
    }
```

**Variable Scope:**
> **Scope** is a characteristic of a variable that defines from which functions that variable may be accessed

there are two variable scrope in c

- **Local variables** can only be accessed within the functions in which they are created

- **Global variables** can be accesssed by any function in the program. 


**Array:**
- We use arrays to hold values of the same type at contiguous memory locations.


when declaring and initializing an array simultaneously, there is a special syntax that may be used to fill up the array with it's starting values.


```c
// instantiation syntax
bool truthable[3] = {false, true, true}

// individual element syntax
bool truthable[3];
truthable[0] = false;
truthable[1] = true;
truthable[2] = true;
```


- arrays can consist of more than a single dimension.
you can have as many size specifires as you wish.

`bool battleship[10][10];`

- you can choose to think of this as either a 10*10 grid of cells.

**Arrays :**
- Recall that most variables in C are passed by value in function calls. 

- Arrays do not follow this rule. Rather, they are **passed by reference.** The callee receives that actual array, not a copy of it. 


**code**
```c
#include <cs50.h>
#include <stdio.h>
void set_array(int array[4]);
void set_int(int x);

int main(void)
{
    int a = 10;
    int b[4] = {0,1,2,3}; 
    set_int(a);
    set_array(b);
    printf("%d %d\n", a, b[0]);
}


void set_array(int array[4])
{
    array[0] = 22;
}

void set_int(int x)
{
    x = 22;
}

```

