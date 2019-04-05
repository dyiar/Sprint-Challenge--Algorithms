Add your answers to the Algorithms exercises here.

a)  a = 0 
    while (a < n * n * n): -- this is o(n) because it is a loop that has multiple non-constant variables being multiplied
      a = a + n * n -- this is o(1) because it is just setting a variable

      the total runtime for this is O(n) because the runtime for this grows the higher input that n is.

b)  sum = 0
    for i in range(n): -- O(n)
      i += 1 -- O(1)
      for j in range(i + 1, n): -- O(n)
        j += 1 -- O(1)
        for k in range(j + 1, n): -- O(n)
          k += 1 -- O(1)
          for l in range(k + 1, 10 + k): -- O(n)
            l += 1 O(1)
            sum += 1 O(1)

    total runtime is O(n^4) because there are 4 for loops and the constants get cancelled out

c)  def bunnyEars(bunnies):
      if bunnies == 0: 
        return 0 -- o(1)

      return 2 + bunnyEars(bunnies-1) -- O(n)

      total runtime is O(n) because the return will happen every time that n>2. 

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.

If I had to find the floor where the eggs aren't broken if dropped from there I would first start on a middle level floor. If the egg broke, I would know that all the floors above me could be removed from testing. Then I would pick a floor in the middle of the old midpoint and the ground. If the broke then we can again remove all the above floors from testing. If it didn't, we could eliminate the lower floors from testing. Continue until you have found the right floor.

The runtime of this solution is O(log n) because the runtime of the solution wouldn't increase that much if n was a bigger number.


  def find_floor(n):
    if n == 0:
      return n

    l = 0
    r = n

    while n > 0:

      mid = l + (r-1)/2;

      if mid returns an unbroken egg:
        r = mid -1

      elif mid returns a broken egg:
        l = mid +1


