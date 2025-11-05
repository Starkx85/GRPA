# WEEK 6 GRPA

## Number 1

```
def percentage_increased(original, new):
    '''Calculate the percentage increase from the original value to the new value.

    Assume original is less than or equal to new.

    Args:
        original (float): The original value.
        new (float): The new value.

    Returns:
        float: The percentage increase.

    Examples:
    >>> percentage_increased(50, 75)
    50.0
    >>> percentage_increased(80, 100)
    25.0
    '''
    if original == 0:
        # Handle edge case where original is 0
        return float('inf') if new > 0 else 0.0
    
    increase = new - original
    percentage = (increase / original) * 100
    return percentage


# Test the function with the provided examples
if _name_ == "_main_":
    # Example usage (commented out to avoid interfering with tests)
    # print(f"percentage_increased(50, 75) = {percentage_increased(50, 75)}")
    # print(f"percentage_increased(80, 100) = {percentage_increased(80, 100)}")
    pass
```


## Number 2
```
def is_ten_digit_even(n):
    '''Checks if a number is a 10 digit even number.
    Also account for negative numbers discarding the sign.
    Args: 
        n (int): The given number. 
    
    Returns: 
        bool : result as True or False. 
    
    Examples:
    >>> is_ten_digit_even(8769473839)
    False
    >>> is_ten_digit_even(928948)
    False
    >>> is_ten_digit_even(9289479278)
    True
    >>> is_ten_digit_even(-9289479278)
    True
    '''
    # Take absolute value to discard the sign
    abs_n = abs(n)
    
    # Check if the number has exactly 10 digits
    # A 10-digit number is between 1000000000 and 9999999999
    if abs_n < 1000000000 or abs_n > 9999999999:
        return False
    
    # Check if the number is even
    return abs_n % 2 == 0
```

## Number 3

```
def arithmetic_operations(t: tuple) -> tuple:
    '''
    Given a tuple of two integers (a, b), return a tuple containing the 
    sum, difference, product, and quotient (integer division) of the two numbers.
    Arguments:
    t: tuple - a tuple of two integers (a, b)
    Return:
    tuple - a tuple containing the sum, difference, product, and quotient
    Example:
    >>> arithmetic_operations((1, 2))
    (3, -1, 2, 0)
    '''
    a, b = t
    
    sum_result = a + b
    difference = a - b
    product = a * b
    quotient = a // b  # Integer division
    
    return (sum_result, difference, product, quotient)
```

## String 1

```
def format_as_second_comma_first(t: tuple) -> str:
    '''Formats the two elements in a tuple as "second, first".
    Arguments:
    t: tuple - a tuple two elements
    Return:
    str - a formatted string "second, first"
    Example:
    >>> format_as_second_comma_first(('hello', 'python'))
    'python, hello'
    >>> format_as_second_comma_first((1, 2))
    '2, 1'
    '''
    first, second = t
    return f"{second}, {first}"
```

## String 2

```
def even_first_odd_reversed(s: str) -> str:
    '''Return a string with the characters in the even indices first 
    and the characters in the odd indices reversed next.
    Arguments:
    s: str - the input string
    Return:
    str - modified string
    Example:
    >>> even_first_odd_reversed('abcde')
    'acedb'
    >>> even_first_odd_reversed('python')
    'ptonhy'
    '''
    even_chars = ""
    odd_chars = ""
    
    # Collect characters at even and odd indices
    for i in range(len(s)):
        if i % 2 == 0:  # Even index
            even_chars += s[i]
        else:  # Odd index
            odd_chars += s[i]
    
    # Reverse the odd characters and concatenate
    return even_chars + odd_chars[::-1]
```

## String 3

```
def is_palindrome(n: int) -> bool:
    '''Checks if an integer is a palindrome.
    Arguments:
    n: int - the integer to check
    Return:
    bool - True if the integer is a palindrome, False otherwise
    '''
    # Convert the integer to a string
    str_n = str(n)
    
    # Check if the string reads the same forward and backward
    return str_n == str_n[::-1]
```

## Collection 1

```
def rotate_list(lst: list, k: int) -> list:
    '''
    Given a list of items and an integer k, rotate the list to the right by k steps.
    Arguments:
    lst: list - a list of items
    k: int - the number of steps to rotate the list to the right
    Return:
    list - the rotated list
    '''
    if not lst:
        return lst
    
    # Handle cases where k is larger than the list length
    n = len(lst)
    k = k % n
    
    # If k is 0, no rotation needed
    if k == 0:
        return lst
    
    # Rotate by taking the last k elements and putting them at the front
    return lst[-k:] + lst[:-k]
```

## Collection 2

```
def swap_alternate_elements(t):
    '''Swap every alternate of adjacent elements in the tuple.
    Args:
        t (tuple): A tuple of even length.
    Returns:
        tuple: A new tuple with alternate elements swapped.
    Examples:
    >>> swap_alternate_elements((1, 2, 3, 4, 5, 6))
    (2, 1, 4, 3, 6, 5)
    >>> swap_alternate_elements(('a', 'b', 'c', 'd'))
    ('b', 'a', 'd', 'c')
    '''
    result = []
    
    # Iterate through the tuple in steps of 2
    for i in range(0, len(t), 2):
        # Swap elements at index i and i+1
        result.append(t[i + 1])  # Add second element first
        result.append(t[i])      # Add first element second
    
    return tuple(result)
```

## Collection 3

```
def in_exactly_one(l1: list, l2: list) -> set:
    '''
    Given two lists, return a list containing the items 
    that are present in either list but not in both.
    Arguments:
    l1: list - the first list 
    l2: list - the second list 
    Return:
    set - a set containing the items present in either list 1 or list 2 but not in both
    Example:
    >>> in_exactly_one([1, 2, 3], [3, 4, 5])
    {1, 2, 4, 5}
    '''
    set1 = set(l1)
    set2 = set(l2)
    
    # Return the symmetric difference (items in either set but not in both)
    return set1 ^ set2
```

## Collection 4

```
def unique_vowels(s: str) -> set:
    '''
    Given a string, return a set of unique vowels present in the string.
    Arguments:
    s: str - the input string
    Return:
    set - a set of unique vowels present in the string
    Examples:
    >>> unique_vowels('banana treat')
    {'a', 'e'}
    >>> unique_vowels('apple lolipop')
    {'a', 'e', 'i', 'o'}
    >>> unique_vowels('Ian Avinkov')
    {'I','A','a','i','o'}
    '''
    vowels = set('aeiouAEIOU')
    return {char for char in s if char in vowels}
```

## Collection 5

```
def common_char_sorted_str(s1:str, s2:str) -> str: 
    '''Returns a sorted string with unique common charecters present in the given strings.
    Arg:
        s1 (str) : Input string. 
        s2 (str) : Input string. 
    Returns: 
        str: string of unique common charecters arranged in ascending order. 
    Examples:
    >>> common_char_sorted_str('apple', 'ball')
    'al'
    >>> common_char_sorted_str('abcde', 'edfci')
    'cde'
    '''
    # Find common characters using set intersection
    common_chars = set(s1) & set(s2)
    
    # Sort the common characters and join them into a string
    return ''.join(sorted(common_chars))
```
