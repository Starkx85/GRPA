# WEEK 7 GRPA

## Numbers 1

```
def seconds_to_minute_seconds(seconds: int) -> tuple:
    '''
    Given an integer representing seconds, return a tuple of (minutes, seconds).

    Arguments:
    seconds: int - an integer representing the number of seconds.

    Return: tuple - a tuple of (minutes, remaining_seconds).
    '''
    # minutes
    
    # remaining
    
    minutes = seconds // 60
    
    remaining = seconds % 60
    
    return (minutes, remaining)
```

## Numbers 2

```

def create_indexed_dict(items: list) -> dict:
    '''
    Given a list of items, create a dictionary with the indices as keys and the items as items.

    Args:
        items (list): A list of items.

    Returns:
        dict: A dictionary with indices as keys and items as items.
    '''
    return {i: item for i, item in enumerate(items)}

    
```

## Numbers 3

```
def manhattan_distance_via_b(a: tuple, b: tuple, c: tuple) -> int:
    '''
    Given three points a, b, and c on the Cartesian plane, 
    calculate the Manhattan distance to go from point a to point c via point b.
    Manhattan distance is the sum of the absolute differences of their Cartesian coordinates.
    Args:
        a (tuple): Coordinates of point a as (x1, y1).
        b (tuple): Coordinates of point b as (x2, y2).
        c (tuple): Coordinates of point c as (x3, y3).
    Returns:
        int: The Manhattan distance from point a to point c via point b.
    '''
    # Distance from a to b
    distance_a_to_b = abs(a[0] - b[0]) + abs(a[1] - b[1])
    
    # Distance from b to c
    distance_b_to_c = abs(b[0] - c[0]) + abs(b[1] - c[1])
    
    # Total distance via b
    return distance_a_to_b + distance_b_to_c
```

## Numbers 4

```
def is_right_triangle_with_even_sides(a: int, b: int, c: int) -> bool:
    '''
    Given three side lengths in the increasing 
    order of length as a, b, and c, where a<=b<=c,
    check if the given sides are the sides of a right 
    triangle whose perpendicular sides are of even length.
    Hint: in a right triangle the square of hypotenuse is the sum of square of other two sides.
    Arguments:
    a: int - the first side length
    b: int - the second side length
    c: int - the hypotenuse length
    Return:
    bool - True if the sides form a right triangle and the perpendicular sides are even, else False
    '''
    # Check if it's a right triangle using Pythagorean theorem
    is_right_triangle = (a * a + b * b == c * c)
    
    # Check if both perpendicular sides (a and b) are even
    both_perpendicular_even = (a % 2 == 0) and (b % 2 == 0)
    
    # Return True only if both conditions are met
    return is_right_triangle and both_perpendicular_even
```

## Strings 1

```
def is_odd_indices_alpha_and_even_indices_digits(string: str) -> bool:
    '''
    Given a string, check if all the odd indices are alphabets and the even indices are digits.
    Note: indices starts from 0.
    Arguments:
    string: str - the input string
    Return:
    bool - True if all odd indices are alphabets and even indices are digits, else False
    '''
    for i in range(len(string)):
        if i % 2 == 0:  # Even index (0, 2, 4, ...)
            if not string[i].isdigit():
                return False
        else:  # Odd index (1, 3, 5, ...)
            if not string[i].isalpha():
                return False
    
    return True
```

## Strings 2

```
def has_a_in_second_half(s: str) -> bool:
    '''
    Given an even-length string, check if the second half contains 
    the character "a" or "A".
    Arguments:
    s: str - an even-length string.
    Return: bool - True if "a" or "A" is found in the second half, else False.
    '''
    # Get the second half of the string
    mid_point = len(s) // 2
    second_half = s[mid_point:]
    
    # Check if 'a' or 'A' is in the second half
    return 'a' in second_half or 'A' in second_half
```

## Strings 3

```
def most_occuring_first_letter(passage: str) -> str:
    '''
    Returns the letter which occurs most frequently 
    as the first letter of any word.(case insensitive)
    Args:
        passage (str): A multi-line string representing the passage.
    Returns:
        str: The most frequently occurring first letter in lowercase.
    '''
    # Dictionary to count first letters
    first_letter_count = {}
    
    # Split the passage into words
    words = passage.split()
    
    # Count first letters
    for word in words:
        if word:  # Check if word is not empty
            first_letter = word[0].lower()  # Get first letter in lowercase
            first_letter_count[first_letter] = first_letter_count.get(first_letter, 0) + 1
    
    # Find the letter with maximum count
    most_frequent_letter = max(first_letter_count, key=first_letter_count.get)
    
    return most_frequent_letter
```

## Strings 4

```
def remove_edges(s: str) -> str:
    '''
    Return a new string with the first two and last two 
    characters removed from the given string. 
    Arguments:
    s: str - a string.
    Return: str - a string with first and last two characters removed.
    '''
    if len(s) < 4:
        return ""
    
    return s[2:-2]
```

## Collection 1

```
def reverse_first_half(t: tuple) -> tuple:
    '''
    Given an even-length tuple, return a new tuple where the first half 
    is reversed, and the second half remains unchanged.
    Arguments:
    t: tuple - an even-length tuple.
    Return: tuple - a new tuple with the first half reversed.
    '''
    mid_point = len(t) // 2
    first_half = t[:mid_point]
    second_half = t[mid_point:]
    
    # Reverse the first half and combine with unchanged second half
    return first_half[::-1] + second_half
```

## Collection 2

```
def delete_first_three(l: list) -> None:
    '''
    Given a list, delete the first three elements in the list.
    Arguments:
    l: list - a list of elements.
    Return: None - the list is modified in place.
    '''
    del l[:3]
```

## Collection 3

```
def number_of_unique_common_digits(n1: int, n2: int) -> int:
    '''
    Given two integers, return the number of unique digits that are common in both numbers.
    Eg, 287498,295424 - 2, 4 and 9 are common to both nums so answer is 3
    Arguments:
    n1: int - the first number
    n2: int - the second number
    Return:
    int - the number of unique common digits.
    '''
    # Convert numbers to strings to get individual digits
    digits_n1 = set(str(abs(n1)))
    digits_n2 = set(str(abs(n2)))
    
    # Find intersection of the two sets and return its length
    return len(digits_n1 & digits_n2)
```

## Collection 4

```
def final_position(pos: tuple, vel: tuple, time: int) -> tuple:
    '''
    Given an initial position of a point moving in a cartesian plane with a constant velocity, 
    find the the final position of the point after a given time. 
    
    Hint: final position = intial position + velocity * time
    Args:
        pos - tuple[int]: A tuple representing the position vector (x1, y1).
        vel - tuple[int]: A tuple representing the velocity vector (vx, vy).
        time - int: time of movement.
    Returns:
        tuple[int]: A tuple representing the displacement (dx, dy).
    '''
    # Extract initial position coordinates
    x1, y1 = pos
    
    # Extract velocity components
    vx, vy = vel
    
    # Calculate final position using the formula: final = initial + velocity * time
    final_x = x1 + vx * time
    final_y = y1 + vy * time
    
    return (final_x, final_y)
```

## Data Processing 1

```
def row_index_with_most_number_of_zeros(matrix: list) -> int:
    '''
    Given a matrix, find the index of the row with the 
    maximum number of zeros in it.
    Arguments: matrix: list[list] 
    Return: int - index of the row with the maximum number of zeros.
    '''
    max_zeros = -1
    max_row_index = 0
    
    for i, row in enumerate(matrix):
        zero_count = row.count(0)
        if zero_count > max_zeros:
            max_zeros = zero_count
            max_row_index = i
    
    return max_row_index
```

## Data Processing 2

```
def courses_sorted_by_enrollment(student_courses: dict) -> list:
    '''
    Given a dictionary of student roll numbers 
    with the list of courses they chose, 
    find the courses sorted from the 
    most number of enrollments to the least.
    Assume no courses will have the same number of students enrolled.
    Args:
    student_courses (dict): 
        a dictionary where keys are student roll numbers and 
        values are lists of courses they chose
    Returns:
    list: 
        a list of courses sorted by the number of students enrolled 
        in descending order
    '''
    # Dictionary to count enrollments for each course
    course_count = {}
    
    # Count enrollments for each course
    for student, courses in student_courses.items():
        for course in courses:
            course_count[course] = course_count.get(course, 0) + 1
    
    # Sort courses by enrollment count in descending order
    sorted_courses = sorted(course_count.keys(), key=lambda course: course_count[course], reverse=True)
    
    return sorted_courses
```

## Data Processing 3

```
def solve():
  """
  Main function to read input, process each sequence, and print the result.
  """
  try:
    # Read the total number of word sequences.
    num_sequences = int(input())
  except (ValueError, EOFError):
    # Handle cases where input is not a number or is empty.
    num_sequences = 0

  # Loop through each sequence.
  for _ in range(num_sequences):
    # Read the line containing the comma-separated words.
    sequence_str = input()

    # Split the string into a list of words and filter out any empty strings.
    # An empty string might occur if there are consecutive commas, e.g., "a,,b".
    words = [word for word in sequence_str.split(',') if word]

    # If there are no valid words after filtering, the longest subsequence is 0.
    if not words:
      print(0)
      continue

    # The minimum possible length is 1 (a single word).
    max_length = 1
    current_length = 1

    # Iterate through the list of words starting from the second word.
    for i in range(1, len(words)):
      # Get the previous and current words for comparison.
      prev_word = words[i-1]
      current_word = words[i]

      # Check for the antakshari property:
      # last letter of the previous word == first letter of the current word.
      if prev_word[-1] == current_word[0]:
        # If the property holds, extend the current chain.
        current_length += 1
      else:
        # If the chain is broken, reset the counter to 1 for the new word.
        current_length = 1

      # Update the maximum length found so far.
      if current_length > max_length:
        max_length = current_length

    # Print the final result for the current sequence.
    print(max_length)

# Run the solution
solve()
```

## Data Processing 4

```
def num_to_word(num: int) -> str:
    '''
    Given an integer, generate a string with its digits as words separated by hyphens.

    Arguments:
    num: int - the input number

    Return:
    str - the string with digits as words separated by hyphens
    '''
    # A list to map digits (by index) to their English word.
    digit_words = [
        'zero', 'one', 'two', 'three', 'four', 
        'five', 'six', 'seven', 'eight', 'nine'
    ]
    
    # Convert the number to a string to easily iterate through its digits.
    s_num = str(num)
    
    # Create a list of words by looking up each digit in the digit_words list.
    # We convert each digit character back to an integer to use it as an index.
    words = [digit_words[int(digit)] for digit in s_num]
    
    # Join the list of words with a hyphen in between each word.
    return '-'.join(words)
```


