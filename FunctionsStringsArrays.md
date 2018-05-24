### Functions

Functions are like building blocks in your code.  You store blocks of code in functions and then 'call' the functions later to run that block of code.

To explain this, think of what currently happens when you click run on your code.  Consider that you have a program like this:

```
int a = 1 //line 1
int b = 2 //line 2
cout << "this is line 3" << //line 3
cout << "end of program" << endl; //line 4
```

Think of the order in which this code will run.  First line 1 will run, then line 2, then line 3 , and finally line 4.  Now let's introduce a function called "add".

```
int a = 1;                         //line 1
int b = 2;                         //line 2
cout << "this is line 3"; <<       //line 3
cout << "end of program"; << endl; //line 4
...
...
...
int add(int op1, int op2){  //line 100
  op1+op2;                  //line 101
}                           //line 102
```

Don't worry about what the function actually does for now, or the syntax.  Let's replace line 3 with a 'call' to our function.

```
int a = 1;                         //line 1
int b = 2;                         //line 2
add(a,b);
cout << "end of program"; << endl; //line 4
...
...
...
int add(int op1, int op2){  //line 100
  return op1+op2;           //line 101
}                           //line 102
```
Remember I said that functions can be called to run their blocks of code.  __That means that whenever a 'call' is seen, the next line of code to run is going to be that function's first line.__
Additionally, after all the function's code has been executed, it's going to skip back to the function call.  So now look at how the code is run:

First line 1 will run, line 2, line 3 __(call to function here),__ then line 100, then line 101, then line 102 __(function is done)__, then back to line 4

This is the basis of how functions work.  Calling functions lets you pause the current code, run the code in a function, and then resume whatever was being run before.

#### Parameters and return value

Functions don't just let you redirect your code, but they also let you __return__ a value from the function.  For example, consider our function 'add'.

```
int add(int op1, int op2){  //line 100
  return op1+op2;           //line 101
}                           //line 102
```

We want this function to __give us back the sum__ of the two numbers we give it.  That's what the 'return' keyword lets you do.  
When the 'return' keyword is seen, your function will end and the value you put after 'return' will be sent back to where you first called the function.

For example, in this function:

```
int c = foo()
int foo(){  
  return 3;         
}                           
```

The variable c is going to be set to 3, because our function is set to 'return 3'.
In c++, you have to declare the type of variable you want to return by including it before the function name.
So if you want to return an int, you would have `int foo(){...}'.  If you want to return a string, you can use 'string foo()...'.
If you don't want to return anything, you can use the `void` keyword.  So your function would look like `void foo()...`.


__Parameters__ let you pass values to a function.  For example, in our function:

```
int add(int op1, int op2){  //line 100
  return op1+op2;           //line 101
}                           //line 102
```

We want to add two numbers.  But how will the function know which two numbers to add?  We give the function this information through parameters.
So look at the above code.  If our function call is `add(3,2)`, then in our function, the variable `op1` will be set to 3, and the
variable `op2` will be set to 2.  Then the function will `return op1+op2` which is equal to 5.

We need to declare what parameters we want when we define the function.  For example, if we want our function to take in a string,
we can have a string parameter.  So our function may look something like `int countCharacters(string s){...}`


### Arrays

Arrays are simply just lists of variables.  Let's say we want to store 3 different numbers in our program.  We can do:

```
int a = 22;
int b = 36;
int c = 45;
```

But that might be kind of ugly.  Instead, we can store these names in an __array__

```
int numbers[3] = {22,36,45};
```

Now, we only have one variable - a list of numbers.  If we want to access any of the numbers in this list, we can do so by specifying the index of the number in the list.
One thing to note here is that in arrays, the index starts at 0.  So for example, we can do `numbers[0] = 5' to change the 1st variable in the list to 5.

You can think of __strings__ as just arrays of characters.  For example, the string `colin` would represent the array ['c','o','l','i','n'].
Consequently you can access each character in a string, but the [syntax is different](http://www.cplusplus.com/reference/string/string/at/)


