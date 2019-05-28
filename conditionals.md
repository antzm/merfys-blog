# Ηow JavaScript evaluates the conditional statements

A few examples on how JavaScript evaluates the conditional statements

# Evaluation of single expressions

## Example 1

```
const x = 1;
const y = 2;

console.log(x === 1 && y === 2);

// console logs: true

```
1. JavaScript evaluates `x===1` to `true`
2. After that, it checks the type of operator
3. The operator is `&&`, so JS needs to continue
   and test the second expression
   in order to reach a safe conclusion
   about he conditional statement.
4. It evaluates `y===2` to true
5. So, it returns the value of `y===2`, which is true

## Example 2

```
const x = 1;
// z should not be declared

console.log(x === 3 && z === 8);

// console logs: false

```
1. JavaScript evaluates `x===3` to `false`
2. After that, it checks the type of operator
3. The operator is `&&`, so JS stops here,
   as it has already reached a safe conclusion
   about the conditional statement.
   So, it doesn't evaluate the second expression
   because regardless of the reuslt, 
   the conditional statement wiil be false.
4. It returns the value of `x===3`, which is `false`


## Example 3

```
const x = 1;
// z should not be declared

console.log(x === 1 && z === 8);

// Uncaught ReferenceError: z is not defined

```
1. JavaScript evaluates `x===1` to `true`
2. After that, it checks the type of operator
3. The operator is `&&`, so JS needs to continue
   in order to reach a safe conclusion
   about he conditional statement.
4. It tries to evaluate `z===8` but,
   as `z` has not been defined, it throws
   a runtime error.
   That error, didin't appear in the previous
   example because JS didn't run that part of
   the code.

## Example 4

```
const x = 1;
// z should not be declared

console.log(x === 1 || z === 8);

// console logs: true

```
1. JavaScript evaluates `x===1` to `true`
2. After that, it checks the type of operator
3. The operator is `||` so JS stops here,
   as it has already reached a safe conclusion
   about he conditional statement.
   It doesn't evaluate the sceond expression
   and for this reason it doesn't throw
   a runtime error as z is not defined.
4. So, it returns the value of `x===1`, which is true.

## Example 5

```
const x = 1;
const y = 2;

console.log(x === 3 || y === 5);
// console logs: false

```
1. JavaScript evaluates `x===3` to `false`
2. After that, it checks the type of operator
3. The operator is `||` so JS needs to continue
   and test the second expression,
   in order to reach a safe conclusion
   about he conditional statement.
4. It evaluates `y===5` to false
5. So, it returns the value of `y===5`, which is false

## Example 6

```
const x = 1;
// z should not be declared

console.log(x === 3 || z === 8);
// Uncaught ReferenceError: z is not defined

```
1. JavaScript evaluates `x===3` to `false`
2. After that, it checks the type of operator
3. The operator is `||` so JS needs to continue
   and test the second expression,
   in order to reach a safe conclusion
   about he conditional statement.
4. It tries to evaluate `z===8` but,
   as `z` has not been defined, it throws
   a runtime error.


## The evaluation process in detail:

To test a conditional statement,
`(firstExpression OPERATOR secondExpression)`
JavaScript does not compare the two expressions side by side.

It rather uses this process:

It always evaluates the first expression.
Then, it always checks the operator.
Depending on the result of the first expression
and the type of operator, it either returns
the result of the first expression and stops,
or, it continues to the second expression,
so, it evaluates the second expression and 
then returns the result of the second expression.


### Example i:  
`(true && ???)`  
JS evaluates the first expression, which is `true`.
Then, it checks the operator which is `&&`
After that, it continues to the second expression and returns
the result of the second expression.

### Example ii:  
`(false && ???)`  
JS evaluates the first expression, which is `false`.
Then, it checks the operator which is `&&`
After that, it returns the result of the first expression.

### Example iii:  
`(false || ???)`  
JS evaluates the first expression, which is `false`.
Then, it checks the operator, which is `||`
After that, it continues to the second expression and returns
the result of the second expression.

### Example iv:  
`(true || ???)`  
JS evaluates the first expression, which is `true`.
Then, it checks the operator which is `||`
After that, it returns the result of the first expression.


# Evaluation of multiple expressions

Now, whenever there are more than two expressions,
JS uses the same process.  
It evaluates an expression to true or false,
checks the next operator, and then it may
continue to evaluate the next expression,
or it may return the result of the last evaluation.  
JS evaluates the expressions starting from 
the left side of the conditional statement
and going towards the right.  
For example, when JS evaluates a very long
conditional statement and has reached the middle of it,
having already evaluated noumerous expressions,
the only thing that JS keeps into memory is
just a true or false value, representing
the total result for all the expressions
that have been evaluated up to that point.
Then, this true of false value will either
be reurned or it may be compared with the
result of the next expression and so on...


## Example A:

```
const a = 10;
const b = 2000; // removing this line, will not throw a runtime error
const c = 3000; // removing this line, will not throw a runtime error

if (a === 10 || a === 15 && b === 20 || b === 25 && c === 30 || c === 35) {
   console.log("the conditional statement is true");
} else {
   console.log("the conditional statement is false");
}

// console logs: "the conditional statement is true"

```

JavaScript tests `a === 10` which is `true`.
Then, it checks for the next operator.
Now, because the operator is `||`
it means that this expression is `true`,
regardless of what lies on the right side of the `||`
So, JavaScript stops the evaluation of
the conditional statement and returns `true`.

This means that the code after the first `||`
will not run at all.
To verify this, we could simply delete
the variable declarations
`const b = 2000;` and `const c = 3000;`
and run the code in a new console window,
and we will notice that the code will run
without throwing an error for 
undeclared variables.



## Example B:

```
const a=10;
const b=2000; 
const c=3000; // removing this line, doesn't throw a runtime error

if ((a === 10 || a === 15) && (b === 20 || b === 25) && (c === 30 || c === 35)) {
   console.log("the conditional statement is true");
} else {
   console.log("the conditional statement is false");
}

// console logs: "the conditional statement is false"

```

JavaScript tests `a === 10`, which is `true`.
Then, it checks which operator is next.
Now, because the operator is `||`
the evaluation of the first parenthesis stops
and the result is `true`.

Going out of the first parenthesis, there is a `&&` operator
To reach a safe conclusion about the conditional statement,
JavaScript needs to evaluate what lies after the `&&` operator.
It checks for `b === 20` which is `false`.
So up to now, the value of the conditional is `false`
but there is a `||` next, so to reach a safe conclusion,
what lies after the `||` needs to be evaluated.
But `b === 25` is `false`, so the whole conditional up 
to this point is `false`.

Next, there is a `&&` operator.
So, JavaScript is right now at the second `&&`
and the left side of the expression,
up to this point is `false`.
So, there is no need to continue.
Regardless of what lies at the right side
of the second `&&`, the conditional statement
is `false`. So, JavaScript stops and returns `false`,
without needing to evaluate the last expression.