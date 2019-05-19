# Examples on how JavaScript evaluates the conditional statements

```
const x = 1;
const y = 2;
```
_Note:
for the following examples,
the variable (constant) z should not be declared_

```
console.log(x === 1 && y === 2);
// console logs: true
```
1. JavaScript evaluates `x===1` to `true`
2. After that, it checks the type of operator
3. The operator is &&, so JS needs to continue
   and test the second expression
   in order to reach a safe conclusion
   about he conditional statement.
4. It evaluates `y===2` to true
5. So, it returns the value of `y===2`, which is true

```
console.log(x === 3 && z === 8);
// console logs: false
```
1. JavaScript evaluates `x===3` to `false`
2. After that, it checks the type of operator
3. The operator is &&, so JS stops here,
   as it has already reached a safe conclusion
   about he conditional statement.
   So, it doesn't evaluate the second expression
   because regardless of the reuslt, 
   the conditional statement wiil be false.
4. It returns the value of `x===3`, which is `false`

```
console.log(x === 1 && z === 8);
// Uncaught ReferenceError: z is not defined
```
1. JavaScript evaluates `x===1` to `true`
2. After that, it checks the type of operator
3. The operator is &&, so JS needs to continue
   in order to reach a safe conclusion
   about he conditional statement.
4. It tries to evaluate `z===8` but,
   as `z` has not been defined, it throws
   a runtime error.
   That error, didin't appear in the previous
   example because JS didn't run that part
   the code.

```
console.log(x === 1 || z === 8);
// console logs: true
```
1. JavaScript evaluates `x===1` to `true`
2. After that, it checks the type of operator
3. The operator is || so JS stops here,
   as it has already reached a safe conclusion
   about he conditional statement.
   It doesn't evaluate the sceond expression
   and for this reason it doesn't throw
   a runtime error as z is not defined.
4. So, it returns the value of `x===1`, which is true.

```
console.log(x === 3 || y === 5);
// console logs: false
```
1. JavaScript evaluates `x===3` to `false`
2. After that, it checks the type of operator
3. The operator is || so JS needs to continue
   and test the second expression,
   in order to reach a safe conclusion
   about he conditional statement.
4. It evaluates `y===5` to false
5. So, it returns the value of `y===5`, which is false

```
console.log(x === 3 || z === 8);
// Uncaught ReferenceError: z is not defined
```
1. JavaScript evaluates `x===3` to `false`
2. After that, it checks the type of operator
3. The operator is || so JS needs to continue
   and test the second expression,
   in order to reach a safe conclusion
   about he conditional statement.
4. It tries to evaluate `z===8` but,
   as `z` has not been defined, it throws
   a runtime error.


## Note:

To test a conditional statement,
(firstExpression OPERATOR secondExpression)
JavaScript does not compare the two expressions side by side.

It rather uses this process:

It always evaluates the first expression.
Then, it always checks the operator.
Depending on the result of the first expression
and the type of operator, it either returns
the result of the first expression and stops,
or, it continues and evaluate the second expression,
and then it returns the result of the second expression

### Example 1:
JS evaluates the first expression, which is true.
Then, it checks the operator which is &&
After that, it continues to the second expression and returns
the result of the second expression.

### Example 2:
JS evaluates the first expression, which is false.
Then, it checks the operator which is &&
After that, it returns the result of the first expression.

### Example 3:
JS evaluates the first expression, which is false.
Then, it checks the operator, which is ||
After that, it continues to the second expression and returns
the result of the second expression.

#### Example 4:
JS evaluates the first expression, which is true.
Then, it checks the operator which is ||
After that, it returns the result of the first expression.


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

