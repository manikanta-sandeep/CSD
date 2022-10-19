# CSD
## Contains Duplicates

```
def cd(nums,k):
  hash_map={}
  for i in range(len(nums)):
    if(nums[i] not in hash_map):
      hash_map[nums[i]]=i
    else:
      if(i-hash_map[nums[i]]<=k):
        return True
      else:
        hash_map[nums[i]]=i
  return False
nums=[1,2,3,1,2,3]
k=2
print(cd(nums,k))
```

## Majority elements in list

```
import math
nums=[1,2,1]
hashmap={}
res=[]
for i in nums:
  if i not in hashmap:
    hashmap[i]=1
  else:
    hashmap[i]+=1
for i,j in hashmap.items():
  if j>math.floor(len(nums)/3):
    res.append(i)
print(res)
```

## Integer to Roman

```
def intToRoman(num):
  i=[1000,900,500,400,100,90,50,40,10,9,5,4,1]
  r=['M','CM','D','CD','C','XC','L','XL','X','IX','V','IV','I']
  a=''
  j=0
  while j < len(i):
    if num-i[j] >=0:
      a += r[j]
      num-=i[j]
    else:
      j +=1
  return a
num=int(input())
print(intToRoman(num))

```

## Maximum string length in a sequence

```
s=input()
if not s:
  max_len=0
max_len=0
start=0
d={}
for i in range(len(s)):
  if(s[i] in d):
    start=max(start,d[s[i]]+1)
  d[s[i]]=i
  max_len=max(max_len,i-start+1)
print(max_len)
```

## Minimum path sum

```
def minPathSum(grid):
  m, n = len(grid), len(grid[0])
  dp = [[0 for _ in range(len(grid[i]))] for i in range(len(grid))]
  dp[0][0] = grid[0][0]
  for i in range(1, n):
    dp[0][i] = dp[0][i - 1] + grid[0][i]
  for i in range(1, m):
    dp[i][0] = dp[i - 1][0] + grid[i][0]
  for i in range(1, m):
    for j in range(1, len(grid[i])):
      dp[i][j] = min(dp[i - 1][j] + grid[i][j], dp[i][j - 1] + grid[i][j])
  return dp[m - 1][n - 1]
grid=[[1,3,1],[1,5,1],[4,2,1]]
print(minPathSum(grid))
```

## No.of paths

```
def numberOfPaths(m, n):
    if(m == 1 or n == 1):
        return 1
    return numberOfPaths(m-1, n) + numberOfPaths(m, n-1)
m = 3
n = 7
print(numberOfPaths(m, n))
```

## No.of Ways

```
def fib(n):
    if n <= 1:
        return n
    return fib(n-1) + fib(n-2)
def countWays(s):
    return fib(s + 1)
 
s = 4
print("Number of ways = ")
print(countWays(s))
```


## Ugly number

```
def maxDivide(a, b):
    while a % b == 0:
        a = a / b
    return a
def isUgly(no):
    no = maxDivide(no, 2)
    no = maxDivide(no, 3)
    no = maxDivide(no, 5)
    if no == 1:
      return 1
    else:
      return 0
def getNthUglyNo(n):
    i = 1
    count = 1  
    while n > count:
        i += 1
        if isUgly(i):
            count += 1
    return i
  
  
no = getNthUglyNo(10)
print(" ugly no. is ", no)
```

## Maximum sequence number in list

```
nums=[100,4,200,1,3,2]
if len(nums)==0:
  print(0)
nums=sorted(nums)
cur,res=1,1
for i in range(1,len(nums)):
  if(nums[i-1]==nums[i]):
    continue
  if(nums[i-1]+1==nums[i]):
    cur+=1
    res=max(res,cur)
  else:
    cur=1
print(res)
        
```


## Total sum equals to target

```
nums=[2,7,11,15]
target=9
for i in range(len(nums)):
  for j in range(i+1,len(nums)):
    if(nums[j]==target-nums[i]):
      print([i,j])

```

