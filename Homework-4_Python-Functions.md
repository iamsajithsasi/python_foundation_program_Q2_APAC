# Python Practice - Session 4


### Task 4.1
Implement a function which receives a string and replaces all `"` symbols
with `'` and vise versa.

```
old_str = "Hello John '\""


def str_change(old_str):
  new_str = ''
  
  for st in old_str:
    if st == '"':
      new_str += "'"
    elif st == "'":
      new_str += '"'
    else:
      new_str += st
      
  return new_str
    
print(str_change(old_str))
```

### Task 4.2
Write a function that check whether a string is a palindrome or not. Usage of
any reversing functions is prohibited. To check your implementation you can use
strings from [here](https://en.wikipedia.org/wiki/Palindrome#Famous_palindromes).

```
check_str = "malayalam"

def checkPalindrome(test_str):
  # reverse string
  rv_string = ''
  test_str_len = len(test_str)
  
  for i in range(test_str_len):
    test_str_len -= 1
    rv_string += test_str[test_str_len]

  return rv_string == test_str
  
print(checkPalindrome(check_str))
```

### Task 4.3
Implement a function which works the same as `str.split` method
(without using `str.split` itself, ofcourse).

```
new_str = "hello world!"

def splitString(old_str, seperator = ""):
  split_string = []

  if seperator:
    counter = 0
    str_len = len(old_str)
    for ch_idx in range(str_len):
      if old_str[ch_idx] == seperator:
        res = old_str[counter:ch_idx]
        split_string.append(res)
        counter = ch_idx + 1
      
      if ch_idx == str_len - 1:
        res = old_str[counter:ch_idx + 1]
        split_string.append(res)
        
  else:
    split_string.append(old_str)

  return split_string
  
print(splitString(new_str, " "))
```

### Task 4.4
Implement a function `split_by_index(s: str, indexes: List[int]) -> List[str]`
which splits the `s` string by indexes specified in `indexes`. Wrong indexes
must be ignored.
Examples:
```python
>>> split_by_index("pythoniscool,isn'tit?", [6, 8, 12, 13, 18])
["python", "is", "cool", ",", "isn't", "it?"]

>>> split_by_index("no luck", [42])
["no luck"]
```

```
def split_by_index(split_str, indexes):
    res = []
  
    left_idx = 0
  
    for ch_idx in indexes:
        tmp = split_str[left_idx: ch_idx]
        res.append(tmp)
        left_idx = ch_idx
    
    if(left_idx < len(split_str) - 1):
        tmp = split_str[left_idx:]
        res.append(tmp)

    return res
  

result = split_by_index("pythoniscool,isn'tit?", [6, 8, 12, 13, 18]);

print(result)
```

### Task 4.5
Implement a function `get_digits(num: int) -> Tuple[int]` which returns a tuple
of a given integer's digits.
Example:
```python
>>> split_by_index(87178291199)
(8, 7, 1, 7, 8, 2, 9, 1, 1, 9, 9)
```

```
def split_by_index(num):
    num_c = str(num)
    res = []
    
    for nm in num_c:
        res.append(int(nm))
     
    return tuple(res)

print(split_by_index(87178291199))
```

### Task 4.6
Implement a function `get_longest_word(s: str) -> str` which returns the
longest word in the given string. The word can contain any symbols except
whitespaces (` `, `\n`, `\t` and so on). If there are multiple longest words in
the string with a same length return the word that occures first.
Example:
```python

>>> get_longest_word('Python is simple and effective!')
'effective!'

>>> get_longest_word('Any pythonista like namespaces a lot.')
'pythonista'
```
```  
def get_longest_word(old_str):
  str_list = old_str.split(" ") 
  tmp = 0
  long_str_idx = 0
  
  for idx in range(len(str_list)):
    ln_st = len(str_list[idx])
    if ln_st > tmp:
      tmp = ln_st
      long_str_idx = idx 
    
  
  return str_list[long_str_idx]
    

long_str = get_longest_word('Any pythonista like namespaces a lot.')
print(long_str)
```

### Task 4.7
Implement a function `foo(List[int]) -> List[int]` which, given a list of
integers, return a new list such that each element at index `i` of the new list
is the product of all the numbers in the original array except the one at `i`.
Example:
```python
>>> foo([1, 2, 3, 4, 5])
[120, 60, 40, 30, 24]

>>> foo([3, 2, 1])
[2, 3, 6]
```

```
def foo(num_list):
  res = []
  
  for nm in num_list:
    agg = 1
    
    for nm_i in num_list:
      if nm_i != nm:
        agg *= nm_i
        
    res.append(agg)
  
  return res
    

print(foo([3, 2, 1]))
```

### Task 4.8
Implement a function `get_pairs(lst: List) -> List[Tuple]` which returns a list
of tuples containing pairs of elements. Pairs should be formed as in the
example. If there is only one element in the list return `None` instead.
Example:
```python
>>> get_pairs([1, 2, 3, 8, 9])
[(1, 2), (2, 3), (3, 8), (8, 9)]

>>> get_pairs(['need', 'to', 'sleep', 'more'])
[('need', 'to'), ('to', 'sleep'), ('sleep', 'more')]

>>> get_pairs([1])
None
```

```
def get_pairs(curr_list):
  pair_list = []
  
  len_curr_list = len(curr_list)
  counter = 0
  
  if  len_curr_list> 2:
    while counter < len_curr_list - 1:
      pr_ls = []
      pr_ls.append(curr_list[counter])
      pr_ls.append(curr_list[counter + 1])
      pair_list.append(tuple(pr_ls))
      counter += 1
  else:
    return
  
  return pair_list  

print(get_pairs([1, 2, 3, 8, 9]))
```

### Task 4.9
Implement a bunch of functions which receive a changeable number of strings and return next parameters:

1) characters that appear in all strings

2) characters that appear in at least one string

3) characters that appear at least in two strings

4) characters of alphabet, that were not used in any string

Note: use `string.ascii_lowercase` for list of alphabet letters

```python
test_strings = ["hello", "world", "python", ]
print(test_1_1(*test_strings))
>>> ('o',)
print(test_1_2(*test_strings))
>>> ('d', 'e', 'h', 'l', 'n', 'o', 'p', 'r', 't', 'w', 'y',)
print(test_1_3(*test_strings))
>>> ('h', 'l', 'o',)
print(test_1_4(*test_strings))
>>> ('a', 'b', 'c', 'f', 'g', 'i', 'j', 'k', 'm', 'q', 's', 'u', 'v', 'x', 'z',)
```

```
import string;

test_strings = ["hello", "world", "python"]

def mapWordCount(word):
  res = {}
  for ch in word:
    if ch in res.keys():
      res[ch] += 1
    else:
      res[ch] = 1
  return res

def test_1_1(*test_strings):
  
  test_strings_list = list(test_strings);
  
  if len(test_strings_list) == 0: return []
  
  init_string = test_strings[0]
  cmp_strings = test_strings[1:]
  
  cmp_arr = []
  cmp_arr_trim = []
  
  output = []
  
  if len(test_strings_list) == 1:
    for ch in init_string:
      if ch not in output:
        output.append(ch)
    return output
  
  
  for string in cmp_strings:
    init_string_map = mapWordCount(init_string)
    
    for ch in string:
      if ch in init_string_map.keys():
        init_string_map[ch] = True
        
    for ch_key in init_string_map.keys():
      if init_string_map[ch_key] is True:
        cmp_arr.append(ch_key)
    
  cmp_arr_trim = mapWordCount(cmp_arr)
  
  for ch_k in cmp_arr_trim:
    if cmp_arr_trim[ch_k] == len(test_strings_list) - 1:
      output.append(ch_k)
     
  
  return output

def test_1_2(*test_strings):
  output = []
  
  for string in test_strings:
    for ch in string:
      if ch not in output:
        output.append(ch)
  
  return output

def test_1_4(*test_strings):
  
  all_chars = mapWordCount(string.ascii_lowercase)
  output = []

  for word in test_strings:
    for ch in word:
      all_chars[ch] = 'True'  

  for ch in all_chars:
    if not all_chars[ch] == 'True':
      output.append(ch)

  return output

def test_1_3(*test_strings):
  output = []
  
  unq_string_arr = []
  
  for string in test_strings:
    unq_string = ''
    for ch in string:
      if ch not in unq_string:
        unq_string += ch
    
    unq_string_arr.append(unq_string)
     
  
  unq_string_ct = {}
  
  for string in unq_string_arr:
    for ch in string:
      if ch in unq_string_ct:
        unq_string_ct[ch] += 1
      else:
        unq_string_ct[ch] = 1
  
  for ch in unq_string_ct:
    if unq_string_ct[ch] > 1:
    # if unq_string_ct[ch] == len(test_strings): #same as test_1_1
      output.append(ch)
  
  return output

print(test_1_1(*test_strings))
print(test_1_2(*test_strings))
print(test_1_3(*test_strings))
print(test_1_4(*test_strings))

```

### Task 4.10
Implement a function that takes a number N as an argument and returns a dictionary, where the key is a n (n ∈ [1, N]) and the value is the square of n (n**2).
```python
print(generate_squares(5))
>>> {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

```
def generate_squares(pow):
  res = {}
  
  if pow <= 0: return res
  
  for num in range(1, pow + 1):
    res[num] = num *num
  
  return res


print(generate_squares(5))
```

### Task 4.11
Implement a function, that receives changeable number of dictionaries (keys - letters, values - numbers) and combines them into one dictionary.
Dict values ​​should be summarized in case of identical keys

```python
def combine_dicts(*args):
    ...

dict_1 = {'a': 100, 'b': 200}
dict_2 = {'a': 200, 'c': 300}
dict_3 = {'a': 300, 'd': 100}

print(combine_dicts(dict_1, dict_2)
>>> {'a': 300, 'b': 200, 'c': 300}


print(combine_dicts(dict_1, dict_2, dict_3)
>>> {'a': 600, 'b': 200, 'c': 300, 'd': 100}
```

```
def combine_dicts(*args):
  
  res = {}
  
  for arg in args:
    for key in arg.keys():
      if key in res.keys():
        res[key] += arg[key]
      else:
        res[key] = arg[key]
  
  return res
```

### Materials
* [Scope](https://python-scripts.com/scope)
* [Functions](https://python-scripts.com/functions-python)
* [Defining your own python function](https://realpython.com/defining-your-own-python-function/)
* [Python Lambda](https://realpython.com/python-lambda/)

