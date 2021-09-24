# Const, Let and Var in JavaScript

The features of ES2015 (ES6) that I want to talk about are const and let. We can use const and let to declare a new variable. I want to explain the basics about how const, var, and let are different.

# **Const**

The variable “const” cannot be reassigned or redeclared. I would say it’s a read-only variable. We use this when we want to declare variables and know that we do not want to change the value later. It is a block scope. It means you cannot access variables outside a block {} once they have been declared inside the block {}. Let me show some examples as follows:

As you can see below, we cannot redeclare const because the error “Uncaught SyntaxError: Identifier ‘test’ has already been declared” is shown.

![img](https://miro.medium.com/max/700/1*mIjWsglkGdKS5zcUpGxdXw.png)

Well, what about we try to reassign a variable? It yelled at me that “Uncaught TypeError: Assignment to constant variable.” Therefore, you cannot reassign this variable.

![img](https://miro.medium.com/max/700/1*98qVZTZ0s6sSuhpzWgzCGQ.png)

# **Let**

The variable “let” cannot redeclared but can be reassigned . It is a block scope. We choose this variable when we want to reassign the value later. We have to declare variables before we use it.

Trying to redeclare for the variable “let” below, shows the error “Uncaught SyntaxError: Identifier ‘test’ has already been declared”. This obviously shows that we cannot redeclare after we have already declared it.

![img](https://miro.medium.com/max/700/1*3XV_ZhnKZx43ZPHojVlwow.png)

Then I tried to reassign the value from “Hello” to “Hi” and the result when we use console.log() is “Hi” and doesn't throw any error. It’s successfully reassigns the variable.

![img](https://miro.medium.com/max/692/1*caP9myvUAibQQBoi0Q5r-w.png)

When we use console.log() to see the value “i” which is out of scope {}, it throws the error “Uncaught ReferenceError: i is not defined”. This is because let is a block scope. As I explained before, we cannot access variables outside the block{}.

![img](https://miro.medium.com/max/700/1*fUaicheO7qU79xVCZz3seg.png)

# **Var**

The variable “var” can be reassigned and redeclared. It’s a function-scope or global-scope. It can be accessed out of scope. We should avoid using “var” because it might lead to bugs in case developers declare variables and redeclare them again.

As seen below, this shows that we can reassign and redeclare the variable var.

![img](https://miro.medium.com/max/636/1*ipMgiTUDtqqkwE79TX1ehA.png)

![img](https://miro.medium.com/max/650/1*gNpuICjPh4wJDUhZH5S8CA.png)

Here is the difference when I tried to access the variables inside the block{}. If I tried to access testConst and testVar, it throws the error that “Uncaught ReferenceError: testConst is not defined”

testConst & testLet cases are as follows:

![img](https://miro.medium.com/max/700/1*_vUYfcUSYjXN-Pn7wySx4A.png)

The testVar example is as follows:

![img](https://miro.medium.com/max/700/1*zb2ZR2_OuloeOI0zNMwLmg.png)

Here is the summary of what we talked about:

![img](https://miro.medium.com/max/700/1*nTUEXjpwXFb7dOAabSDZPg.png)

**Resources**

1. https://www.w3schools.com/js/js_scope.asp
2. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const
3. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let
4. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var