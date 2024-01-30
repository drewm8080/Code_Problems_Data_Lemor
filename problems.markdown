### Factorial
```PYTHON
def factorial(n):
  # start out the number
  full_answer =1
  # loop through 1 to the full number
  for i in range(1,n+1):
    # multiply by 1,2,3,4,5 etc to the answer until you have the full number. Rewrite the number 
    full_answer = full_answer *i
  return full_answer
```
### Fizz Buzz Sum
```Python
def fizz_buzz_sum(target):
  multiple_3_5 = []
  # looping through
  for i in range(1,target):
    # if the number is divisble by 3
    if i %3 == 0:
      multiple_3_5.append(i)
    # if number is divisible by 5 
    elif i %5 == 0:
      multiple_3_5.append(i)
  # returning final sum 
  final_number=sum(multiple_3_5) 
  return final_number

# now the actual answer
def fizz_buzz_sum(target):
  sum = 0
  for i in range(target):
    if (i % 3 == 0) or (i % 5 == 0):
      sum += i
  return sum
```

### Intersection of Two Lists 
```Python
# first attempt
def intersection(a, b):
  new_list=[]
  for i in a:
    if i in b:
      new_list.append(i)
      
  return new_list

# second attempt
def intersection(a, b):
  a_set = set(a)
  b_set = set(b)
  final_list = a_set.intersection(b_set)
  return list(final_list)
  return new_list
```

### 

```Python
# first attempt:
def missing_int(input: list[int])-> int:
  input.sort()
  count = 0
  for i in input:
    if i!= count:
      return count
    count+=1
  return len(input)



# second attempt:
def missing_int(input: list[int])-> int:
  input.sort()
  count = 0
  for i in range(len(input)):
    if input[i] != i:
      return i
  return len(input)

# problem with the above? Sorting a list has a time complexity of O(log*n)

# hash set (set automatically orders)


# better solution
def missing_int(input: list[int])-> int:
  set_list = set(input)
  for i in range(len(set_list) + 1):
    if i not in set_list:
      return i


```

### Contains Duplicate
```Python
def contains_duplicate(input)-> bool:
  set_input = set(input)
  # doesnt contain duplicates
  if len(set_input) == len(input):
    return False
  # contains duplicates
  else:
    return True

# dictionary solution
def contains_duplicate(input)-> bool:
  seen_dictionary = {}
  for i in input:
    if i in seen_dictionary:
      return True
    seen_dictionary[i]=True
  return False


```

### Inquity

```Python
def min_inequity(salaries, n):
	salaries.sort()
	minimum_salary = min(salaries[:n])
	maxiumum_salary =max(salaries[:n])
	return maxiumum_salary-minimum_salary
```

### max_profit
```Python
def max_subarray_sum(prices):
  max_profit = 0
  for i in range(len(prices)-1):
    # seeing each number and seeing which is greater
    for j in range(i+1,len(prices)):
      profit = prices[j]-prices[i]
      if profit>max_profit:
        max_profit = profit
  return max_profit


```


### Factorial Trailing Zeroes [Microsoft Python Interview Question]

```Python
def trailing_zeroes(n):
  def factorial(n):
    final_answer= 1
    for i in range(1,n+1):
      final_answer = i*final_answer
    return final_answer 
    
  factorial_number = factorial(n)
  num_zeros = 0
  while factorial_number %10 ==0:
    num_zeros+=1 
    # floor division to remove each zero at the ened
    factorial_number //=10
  return num_zeros


```


### Maximum Product of Three Numbers [D.E. Shaw Python Interview Question]

```Python
def max_three(input):
    new_list = sorted(input)
    a = new_list[-1] * new_list[-2] * new_list[-3]
    two_smallest_number = new_list[0] * new_list[1]
    b = two_smallest_number * new_list[-1]
    maximum = max(a, b)
    return maximum
```

### Two Sum [Amazon Python Interview Question]

```Python
def two_sum(input: list[int], target: int) -> list[int]:
  for i in range(len(input)):
    for j in range(i+1, len(input)):
      print(i,j)
      if input[i]+input[j] == target:
        return [i,j]
  return [-1,-1]

two_sum([1,2,3,4],7)

# printed version

0 1
0 2
0 3
1 2
1 3
2 3
[2, 3]
```

### Largest Prime Factor [Facebook Python Interview Question]


```Python
def largest_prime_factor(target):
  smallest_prime = 2
  # number must have a number smaller than its square root 
  while smallest_prime*smallest_prime <= target:
    if target % smallest_prime != 0:
      smallest_prime+=1
    else:
      # keep dividing to get smallest prime
      target = target//smallest_prime
  return target
      
```

