# Week One video-2 notes:

## Today we are going to focus on.
- Variables and types
- Input and printing
- Function, loops and conditionals
- problem set 1


## Variables 
variables is a way of storing information inside of a computer.

**Q-: How would you describe a variable in a single sentence ?**

How would you explain what a **variable** is, in a single sentence?

**Ans: A variable is a name for some value that can change**


```c
    // Example of variable 
    int calls = 3;

/*
    call - is a name of the variable
    int - type. what type of value take in this variable 
    3 - is the value of the variable 
    = - assignment operator
*/ 

/*
    "Create an integer named country_code that gets the value 65"

    or

    that container that is an iteger called country_code that will get the value of 65
*/ 


```

# Command Line

- The cs50 IDE is a cloud-based machine running Ubuntu, one of the many flavors of the Linux OS.
- Many morder Linux distributions have graphical user interfaces ***(GUI)** to allow easy mouse-based navigation. 
- Still, as a programmer you'll likely be using  your terminal window frequently, and you can do many of the same tasks with keyborad commands.

## Using the linux command line
- let's have a look at some of the most important of these keyborad-based commands for working within the IDE or any UNIX-based system. 

1. `ls`
- Short for "list", this command will give you a readout of all the files and folders in your current directory. 

2. `cd`
- change directory

3. `ctrl + l`
- 'clear the directory'

4. `pwd`
-  present working directory, it will provide me the path of the directory 

5. `cd`
-  if i press just cd it will move me the past directory. 

6. `makdir`
- make a drectory

7. `cp`
- copy. This command will allow you to create a duplicate of the file.

8. `cp -r`
- If you wish to copy entire directoires, you'll need to modify the command slightly `cp -r`  "-r" stands for recursive, and tells cp to dive down into the directory and copy everything inside of it. 

**Example-1:** cp hello.c   hi.c 
- hello.c's everything will copy my new hi.c's file

**Example-2:** cp -r pset0 pset3
- her pset0's all thing will copy to my new folder call pset-3


9. `rm`
- remove, this cammand will delete file after it asks you to confirm **(y/n)** you want to delete it.

- you can remove all file  by typing: `rm -f` 

- To delete entire directories you need to use the`rm -r` -r flag, as was the case with `cp`. 

- you can also combine the `-r` and `-f` flags into `-rf`. agian, careful! There's no undo!. 

10. `mv`
- move. it will rename the file or folder.

**Example:** move gredy.c greedy.c

 








