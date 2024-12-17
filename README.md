# MongoDB Aggregation: Handling Empty Lookup Results in $unwind
This repository demonstrates a common error when using the `$lookup` and `$unwind` operators in MongoDB aggregation pipelines.  The issue arises when the `$lookup` stage returns an empty array, leading to an error in the `$unwind` stage.

The `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using `$unwind` with the `preserveNullAndEmptyArrays: true` option or an alternative approach using `$ifNull` and `$map` to handle cases when the joined collection does not provide a match. 

## Problem
The `$unwind` operator in MongoDB is used to deconstruct an array field from the input documents. However, it throws an error if the array is empty.

## Solution
The solution involves handling cases where the `$lookup` stage doesn't find a match in the target collection.

This solution involves two techniques: 
1. Using the `preserveNullAndEmptyArrays` option in `$unwind`
2. Using an alternative approach using `$ifNull` and `$map`. 

Choose the method that better suits your needs.