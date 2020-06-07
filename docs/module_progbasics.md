# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
You can store different data types , and you can iterate over it .
append(),len(),count()
#### What is the difference between a list/array and a set?
You can declare a list like lst=[] but the set is like set={}, a list can contain duplication , the set isn't.
#### What is the purpose and methods of a dictionary/map data structure?
The dictionary can contain Key/Value pairs which is very useful in many cases .
### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
def Fibonacci():
    Fibonacci_list = [1, 2]
    for i in range(20):
        next_element = Fibonacci_list[-1] + Fibonacci_list[-2]
        Fibonacci_list.append(next_element)

#### How do you find a max value in a list/array if you can’t use any built-in functions?
def find_max():
    max_list = [1, 21, 33, 4, 5, 6]
    max = 0
    for number in max_list:
        if number > max:
            max = number
    return max
#### How do you find the average of values in a list/array if you can’t use any built-in functions?
def find_average():
    average_list = [1, 21, 33, 4, 5, 6]
    sum = 0
    counter = 0
    for number in average_list:
        sum += number
        counter += 1
    return sum/counter.
#### What do we call an *in-place* sort?
Sorting a variable, in-place. Meaning sorting temporary.
#### Explain an algorithm which sorts a list!
The bubble sort , it goes trough on all the elements of the list , checking the elements relations next to each other, if the next element is lower, swap them. It goes until the full list will be sorted.
### Programming paradigms - procedural

#### What is the call stack?
Stack can be a list , the main function of the list is we can put element only to top of the list like list.append() and we can delete like LIFO last in first out list.pop()
#### What is “Stack overflow”?
The stack has a limited space to store , if we want to put more element than the available place it will throw stack overflow error.
#### What are the main parts of a function?
```Python
def function_name(function_arguments):
    body_of_the_function=[]
    return body_of_the_function4
```
### Programming languages - Python  
#### How do you use a dictionary in Python?
dict = ['key1':'value1', 'key2':'value2', 'key3':'value3'] declaration
dict[key1] we can see the key1`s pair value
dict[key2]='other key'	we can add a new value to the keys
dict.update('key4':'value4') we can add new key value pairs to the dict
#### What does it mean that an object is immutable in Python?
You can't change the elements value after declaration.
#### What is conditional expression in Python?
a, b = 3, 2
is_a_bigger_than_b = True if a > b else False
#### What are different types of arguments in Python?
def funct(*args, **kvargs):
    print(args)
    print(kvargs)


funct(1, 2, 5, 7, h='a', c='444')

we can use arguments as an input to the function if we know how many arguments will be used as input we can use:
def funct(a,b):
if we don't
def funct(*args):
we can add many arguments as input to the function
but we can add a dict as an input as well
def funct(**kvargs):

#### What is variable shadowing? (context: variable scope)
The variable shadowing means when you declared a variable in a function, that variable exist in the function only, if you want to use somewhere else, you have to declare again.
#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
If you use for loop, if you delete an item from list , that will run less times, if you add an item to a list it will run forever.
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
The variable only available at that region where it was created.
If you declare inside a loop , you can use only in that function.
#### If you need to access the iterator variable after a for loop, how would you do it in Python?
You can assign it to a new variable in the loop.
#### What type of elements can a list contain in Python?
Boolean,
string
float
integer
lists
dict
tuple
#### What is slice operator in Python and how to use?
Slice operator is used when you want only a slice of the list.
like:
print(list[from(included):until(not included)])

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?

#### What is the purpose of the in and not in membership operators in Python?
Check if an element is in or not in the list , if the element is in the list it returns True , else returns False
#### What does the + operator mean when used with strings in Python?
It will concatenate the two strings.
#### Explain f strings in Python?
f strings is a good way to build up strings.
f{stringVariable1}add something{stringVariable2}add something{stringVariable3}
#### Name 4 iterable types in Python!
list
string
dict
tuple
#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
the list can contain duplication's and single elements. list[1,1,5,6]
a set can contain single elements an unordered way. set{9,2,6,5}
The dict can contain key-value pairs dict{1:'something',2:'apple'}
#### Does the order of the function definitions matter in Python? Why?
It's doesn't matter just help you understand if you ordering.
#### What does unpacking mean in Python?
Unpacking means you can declare many variables in one line:
a, b, c = 1, 2, 3
or you can use a return value of a function and assign to a variables:
a, b = my_funct()
#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?
The value of the element will be 'None'
## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
print()
debugger
rubber duck
#### What does step over, step into and step out mean while using the debugger?
step over : if you push that button it goes step by step but doesn't go into the functions, just step on it and go trough
step into : if you push, you can deeply go step by step, it going into the function as well.
step out: if you are in one function that button will exit from that function.
#### How can you start to debug a program from a certain line using the debugger?
You can mark lines with a red dot where you want to stop the program and after on a left side click on the debugger, after choose 'debug a currently open file'.
### Version control

#### What are the advantages of using a version control system?
It makes the collaboration easier , you will have backup after every commit.
#### What is the difference between the working directory, the staging area and the repository in git?
working directory where you working on your computer , staging area where your commits will be placed before pushing up to the repository.
#### What are remote repositories in git?
The remote repository is an online storage of the codes where you can work together with your colleagues by push and pull the modifications.
#### Why does a merge conflict occur?
It happen when two people modify a same thing and the git can not decide what modification is official.
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
git add 'file name'
git commit -m 'meaningful commit'
git push
#### What does it mean atomic commits and descriptive commit messages?
Atomic commit means when you explain more than one change in one commit messages.
describe commit means you clearly explain in the commit what happened.
#### What’s the difference between git and GitHub?
Git is a version control system.
the GitHub is one of the version control systems

## Software design

### Clean code

#### What does clean code mean?
No duplication's.
No dead codes.
Meaningful variable names.
no magic numbers
#### What steps do we usually do during a clean code refactoring?
Delete dead code .
put duplication's into functions.
renaming variables
### Error handling

#### What is exception handling?
Error can happens during execution of a program.
When that error occurs, you can create exception to handle it, to avoid your program to crash.
#### What are the basics of exception handling in Python?
using the try-except block
#### In which case should we catch an exception? Why?
when we want to read a file by filename what was given by the customer, and handle if that file names doesn't exist.
#### What can/should we do with an exception in the ‘except’ block?
print an understandable error message 
#### What does the else and finally statement do in a try-except block in Python?
If none of the conditions are True it will execute the else block and it docent matter which condition was true before , the program in the finally block will execute always.
## Software Development Methodologies

#### What is the main goal of a retrospective meeting?
To summarize the week , what was bad , what was good, how can we improve from it.

## Programming environment

### Unix

#### What is UNIX and what is Linux?
both is an operating system the Linux rather on PCs UNIX on servers, the Linux is based on UNIX.
#### What do we call the shell in Linux?
It is a program that takes commands from the keyboard and gives them to the operating system to perform
#### What does root means in a Linux environment?
Administrator environment . You have access to all the commands and files.
#### How do you access your personal files in Linux?
You need to be superuser in terminal and cd command or you can use file manager.
#### How can you install an application in Linux?
You can use the software center , or in terminal sudo 'filename' install command.
#### What is package management in Linux, what are repositories?
package managers are collections of software tools that automates the process of installing
#### How do you navigate in the filesystem with the command line?
cd 'folder name' to step in to folder
ls to have a list of files in current folder
cd .. step back to the previous folder.
#### What does the following commands do: mkdir, rm, cat, cp, touch?
mkdir -make a folder 
rm -delete
cat - list the text inside the file
cd - copy
touch - make a new file
#### How can you look up what does a command do in Linux if you have no internet connection?
--help
#### What does the following commands do: head, tail, more, less?
- more : to view a text file one page at a time, press space bar to go to the next page
- tail : display the last part of the file
- head : displays the first ten lines of a file, unless otherwise stated.
- less : read contents of text file one page(one screen) per time. It has faster access because if file is large, it don’t access complete file, but access it page by page. it is similar to "more" command
#### How do you download a file from internet using the terminal?
Using wget "http>//something.com/file.txt"
