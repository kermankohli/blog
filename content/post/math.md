# An overview of modular arithmetic and relations

What's the big deal about modular aritmetic you may ask? Well, it's basically the precursor to number theory, which is a cornerstone of cryptography. This post is an attempt to lay all of it out in a simple way for you to understand.

## Divisibility

Let's take two integers: `a` and `b`. Now let's introduce a new integer called `m` so that `b=a*m`.

Simple right? We can actually express this relation in a few ways:
```
- b is a multiple of a
- b is divisible by a
- a is a divisor of b
- a is a factor of b
```

We can express this relation via the following notation: `a | b` 
> a is a divisor/factor of b.


There's actually some pretty interesting implications of this. For example:
- If `a | b` then `a | bc`. 
	- If `a` is a factor of` b`, then it'll be the factor of `b` no matter what `b` multiplied with.

- If `a | b` and `a | c`, then `a | (b + c)`. 
	- If `a` is a factor of `a` and `c`, then it'll a factor of `a + c`. For example, if `5` is a multiple of `10` and `15`, it will also be a factor of `25`.

- If `a | b` and `a | c`. then `a | (sb + tc), for all integers s & t`. 
	- This expands on the above but states that  multipliers of any factor won't impact the divisibility.

- If `a | b` and `b | c`, then `a | c`. 
	- This can be a bit hard to get your head around is quite straight forward. Let's say `a=3`, `b=6` and `c=12`. Since `a is a factor of b` and `b is a factor of c`, then due to transitivity `a must also be a factor of c`.

### Prime Numbers

As you may remember from school, a prime number is such that it can only be divided by itself. The first few prime numbers are: `2, 3, 5, 7, 11, 13, 17, 19, 23, 29`.

If we wanted to find the prime factors of 345 we could do the following:
	- `3 * 115 = 3 * 5 * 23`
	- `5 * 69 = 5 * 2 * 23`

So how can we quickly check whether a number is prime or not without having to list all the factors.