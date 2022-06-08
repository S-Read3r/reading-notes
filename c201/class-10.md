# Understanding Handling and Debugging

JavaScript can be hard to learn and everyone makes mistakes when writing it. This chapter will help you learn how to find the errors in your code. This chapter will also teach you how to write scripts that deal with potential errors.

There are ways of which us as programmers are given to find errors in our code.
    - The Console and Dev tools.
    - Common Problems.. things like stackover flaw
    - Handling Errors.. The attitude when one encounters an error.

### Order of execution

To find the source of an error, it helps to know how scripts are processed. the order in which statements are eecuted can be complex; some tasks cannot complete until another statement of function has been run:
```js
    function greetUser() {
        return `Hello ${getName}`;
    }

    function getName(userName) {
        let name = username'
        return name;
    }

    let greeting = greetUser();
    alert(greeting);
```
1. The greeting variable gets its value from the greetUser() function
2. greetUser() creates the message by combining the 'Hello ' with the result of getName();
3. getName() returns the name to greetUser();
4. greetUser() now knows the name, and cmbines it with the string. It then return the message to the statement that called it in step 1.

1. The value of the greeting is stored in memory. 
4. This greeting variable is written to an alert box.

### Execution contexts

The JavaScript interpreter ises the concept of execution xontexts. There is one global execution context; plus each function creates a new new execution context. They correspond to variable scope.

## The Stack

The JavaScript interpreter processes one line of code at a time. when a statement needs data from another function , it stacks (or piles) the newfunction on top of the current task.
when a statement has to call some other code in order to do its job, the new task goes to the top of the pile of things to do. 

Once the new task has been perfomed, the interpreter can go back to the task in hand. Each time a new item is added to the stack, 