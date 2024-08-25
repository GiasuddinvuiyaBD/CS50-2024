# CS50X Notes (lecture-0)

--
## what is problem solving
1. you've got some input, the problem to be solved
2. You've got a goal being the output, like the solution there, too

3. and then somewhere in the middle is the secret sauce, where we'll spend the next several weeks figuring out how we can convert thise inputs to outputs.

## what is unary and binary number

1. Unary means what computer representing like number or any information that we see but bahind of this binary numbers which is 0 and 1. 0 represent false and 1 represent true.

`bit`, it just means binary digit. a single bit just 0 and 1.

`Binary`, it's the permutations, which ones are on and off

`Byte`, means eight bits. 
example:
 `00000000` and this
`11111111` using 1 bit. 

Now you've got to do some quick math-- represents what number, instead **`?`**

So, it's indeed `256`

calculations `1*2*4*8*16*32*64*128` equal to `256`


**Any QUESTIONS on binary unary, or the like?** No.


### How do you represent letters ?

For representing letter **`A`** Under neeth it `ASCII` number is `65`. It's actually storing a pattern of 0's and 1's that represents the number `65`;

`ASCII` Stand for American standert code for information interchange.

2. QUESTION-2: How many possible letters of any alphabet could we represent with eight bits??

**`Ans: 256`** 
Note: Download an ASCII Table form internet and check it out.



## For Emoji we use Unicode.

Unicode doesn't just use eight bits. It sometimes uses 16 bits per character, sometimes 24 bits per character and sometimes even 32 bits per character.

so, why this numbers ? That's just one byte, two bytes, three bytes, or four bites.

Unicode 
`U+1F602`
U+ Represent unicode charactor.

picture,song,movie all are play with unicode.



## Algorithm or "step-by-step instructions" ? 


Our goal is not to write and solve problem correctly, but, ultimately, ever more efficiently as well. 


## Let's talk about Pseudocode

Pseudocode has no formal meaning. Generally, you write it in English or whatever your own human language is.
But you write your thoughts down tersely, succinct, but precisely. You try to really convey your thoughts, not with a wave of the hand metaphorically, but step by step, precisely. 

So, what i mean by this? 

Here might be some representative pseudocode.

via which i describe that third and final algorithm in a way. That i could hand it to you and you could do the same at home.

Or I could hand it to someone at Googlem and they could implement it in Android.

Or I could hand it to someone at Apple, and they could implement it in iOS.

**Example: Algorithm steps**
1. Pick up phone book
2. Open to middle of phone book
3. Look at page
4. If person is on page.
5.      call person
6. Else if person is earlier in book
7.       Open to middle of left half of book
8.        Go back to line 3
9. Else if person is later in book.
10.       Open to middle of right half of book
11.        Go back to line 3

12. Esle
13.   Quit.

## Few Building Blocks

```js
    functions
    conditions
    Boolean expressions
    loops
```

## Artificial Intelligence

In this course we will learn how to use AI.

Sorry

#### Not Reasonalble
Using AI-based software other than CS50's own...


### CS50 Duck 
CS50.ai

web-base application like chatGPT

**LLM** stand for Large language models. 


Note Link: https://cs50.harvard.edu/x/2024/notes/0/#computer-science 



# CS50X Notes (lecture-1)

Note: Computer know only about binary number. but we are going to write sourcese code. compiller will convert source code into machine code.


We will use vs code for c programming.

we have two interface
1. Graphical interface
2. cmd command line interface


for writing code in js code. i have to install cs50.dev

for opening the c program file.
i have to write code on command line **`code hello.c`**

then we will write our first program in c.

```c
#include <stdio.h>


int main(void)
{
    printf("hello, world");

    printf("hello, world/n"); // it will create new line at the end of my output
}

// for seeing it's output we have to go to terminal. and write

make hello // which is our file name then 
.hello // enter

```

here is : 
1. `#include <stdio.h>` is a library that someone else wrote that we can use.
2. `printf()` fun come form stdio.h libries.

for learn more about this we can go cs50 `Manual Pages` **`manual.cs50.io`**

note: manual.cs50.io/#stdio.h



## Now we will take value from user.

```c 
    #include <cs50.h>
    #include <stdio.h>

    string answer = get_string("What's your name? ");

    // printf is a function for showing ouput
    printf("hello, %s\n", answer);
    // %s is a placeholder.
```

## Data types of c

- bool
- char
- double
- float
- int
- long
- string


## for taking user input
- get_char
- get_double
- get_float
- get_int
- get_long
- get_string

## format code 
- %c // char
- %f // float
- %li // integer
- %s // string

## condition

```c

    if(x < y>)
    {
        printf("x is less than y\n")
    }

    if(x < y>)
    {
        printf("x is less than y\n")
    }else if(x == y)
    {

    }else{
        printf("x is grater than y\n")
    }
    

```
## variable in C

```c
    int counter = 0; 
    // incremental
    counter = counter + 1;
    // or
    counter += 1;
    // or 
    counter++;

    // opposit
    counter--
```

## run the code in terminal
```c
//code compare.c its our file name
    #include <sc50.h>
    #include <stdio.h>

    int main(void)
    {
        int x = get_int("What's x?")
    int y = get_int("What's y?")

    if(x < y){
        printf("x is less than y\n")
    }

/*
    run the code 
    ____________
    make compare 

    ./compare // how i run the program
*/

    if(x < y>)
    {
        printf("x is less than y\n");
    }else if(x > y)
    {
        printf("x is greater than y\n");
    }else{
        printf("x is equal to y\n");
    }

    }
```


## char data type
char data types provide us a single charactor in c. specially yes no question

```c
    #include <cs50.h>
    #include <stdio.h>

    int main(void)
    {
       char c = get_char("Do you agree? ");

       if(c == 'y' || 'Y')
       {
        printf("Agreed.\n");
       }else if(c == 'n' || 'N')
       {
        printf("Not agreed.\n");
       }
    }

/*
    make agree
    ./agree
    
*/

```

## Another building block namely loops.

```c
    #include <cs50.h>
    #include <stdio.h>
int main(void)
{
    int i = 3;
    while(i > 0)
    {
        printf("meow\n");
        i = i - 1
        // or
        i -= 1
        // or
        i--
    }


    // another way 

    int num = 0;
    while(num < 3)
    {
        printf("moew\n"); 
        num++;
    }

// another way to perform loop

    for(int i = 0; i < 3; i++)
    {
        printf("meow\n");
    }
}

/*

code meow.c
make meow
./meow

*/ 
```


## function in c 

We can declare a function insted of main

```c
void meow(void)
{
    printf("meow\n")
}

/*
 1. void this function has no return value.
 2. (void) it takes no input it only takes meow.
 3. when i need meow val just we should call it inside the main fun
 4. we should declare main fun lower of every fun.
*/

int main(void)
{
    for(let i =0; i < 3; i++)
    {
        meow()
    }
}


// another way we can declare a fun

//inside the meow function i have to tell the type of input
void meow(int n)
{
    for(int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}


int main(void)
{
    // here i have called meow fun and pass the value to meow fun. 
    meow(3)
}

```



## Second part of the class
Here we are going to make calculator. 

```c
    #include <cs50.h>
    #include <stdio.h>

    // this is the prototype of the add fun
    int add(int, a, int b);

    int main(void)
    {
        int x = get_int("x: ");
        int y = get_int("y: ");

        int z = add(x, y); 

        printf("%i\n", z);
    }

    // declear add fun with two paramiter
    int add(int a, int b)
    {
        return a + b
    }
```

<!-- /*
    run the program
    ________________
    code calculator.c
    make calculator
    ./calculator
*/  -->


Note: **`Linux is most popular oporating system`**

and it's very commonly used for servier nowadyas.

It's command line interface. and also GUI or Graphical user Interface.

**Some command line commands**

- cd 
- cp 
- ls 
- mv
- rm
- rmdir 

practice it 
-- 
`rename file` **`mv meow.c woof.c`**

`list directory` **`li`**

`remove file` **`rm hello.c`**

`go to new directory` **`cd folder name`**

`make folder` **`mkdir folder name`**

`remove folder` **`rmdir folder`**


## Now watch game image then make program

```c
#include <cs50.h>
#include <stdio.h>

// we can use constant num in c

const int n = 5;
int num;

int main(void)
{

    do{
        num =  get_int("Size: ");
    }while(num < 1)

    for(int i = 0; i < n; i++)
    {
        for(int j = 0; j < n; j++)
        {
            printf("#")
        }
    }
    printf("\n")
}

/*
    make mario
    ./mario
*/

```

## Type casting in cs 
we are converting one type to another. 


```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int x = get_int("x: ");
    int x = get_int("y: ");

    float = z (float) x / (float) y;

    // we have converted string type to floating number.

    printf("%f\n", z);
    // printf("%.3f\n", z);
}
```






