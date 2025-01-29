# F# Mutable Variable Swap Bug

This repository demonstrates a common error in F# related to mutable variables and the way function parameters are handled. The code attempts to swap two mutable variables using a function, but due to pass-by-value semantics, the swap operation doesn't affect the original variables.

## Bug Description
The `swap` function intends to exchange the values of `x` and `y`. However, because F# parameters are passed by value, the function receives copies of `x` and `y`.  Modifying these copies has no effect on the original variables outside the function's scope.

## Solution
The solution involves passing the variables by reference using `byref` and appropriately updating the variables in the function.