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
