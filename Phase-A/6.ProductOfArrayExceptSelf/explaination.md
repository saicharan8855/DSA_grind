# Product of Array Except Self – Prefix and Suffix Approach

## What’s the problem asking?

You’re given an integer array `nums`.

For each index `i`, return a new array where `answer[i]` is the product of **every element except `nums[i]`**.

Example:

- `nums = [1,2,3,4]` → output = `[24,12,8,6]`

Why?

- At index `0`: multiply `2 × 3 × 4 = 24`

- At index `1`: multiply `1 × 3 × 4 = 12`

- At index `2`: multiply `1 × 2 × 4 = 8`

- At index `3`: multiply `1 × 2 × 3 = 6`

So the result becomes `[24,12,8,6]`.

---

## The brute force idea

The most direct idea is simple:

for every index `i`, loop through the whole array again and multiply everything except `nums[i]`.

### Brute force code

```python
def product_except_self_brute(nums):
    n = len(nums)
    result = []

    # For each position, multiply everything except itself
    for i in range(n):
        product = 1
        for j in range(n):
            if i != j:           # skip the current index
                product *= nums[j]
        result.append(product)

    return result
