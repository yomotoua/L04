# Bug reports for exercise1.py

Line: 3
Problem: The function `is_even(n)` returns `True` for odd numbers because it checks `n % 2 == 1`, which is correct for odd numbers, but the docstring says "true for even numbers", which is incorrect.  
Example: (`is_even(2)` returns `False`, expected `True`. `is_even(3)` returns `True`, but should return `False`. )  
Fix: `return n % 2 == 0`

Line: 8
Problem: The function `rectangle_area(width, height)` returns the sum of width and height, but the docstring describes it as the "area of a rectangle", which should be width times height.  
Example: (`rectangle_area(4, 5)` returns `9`, expected `20`. )  
Fix: `return width * height`

Line: 12
Problem: The function `double(n)` adds 2 to the input, but the docstring says "twice the number n", which means it should return `n * 2`.  
Example: (`double(3)` returns `5`, expected `6`. )  
Fix: `return n * 2`
