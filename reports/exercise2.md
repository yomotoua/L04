# Bug reports for exercise2.py

Line: 3  
Problem: The docstring says "True if the grade is 5 or more", but the function uses `grade > 5`, which means it returns False for a grade of exactly 5.  
Example: is_passing(5) returns False, but it should be True according to the docstring.  
Fix: return grade >= 5

Line: 8  
Problem: The docstring says "At least 8 characters", which means length >= 8, but the function uses `len(password) > 8`.  
Example: is_valid_password("abcdefgh") returns False, but it should be True since it has exactly 8 characters.  
Fix: return len(password) >= 8 and any(c.isdigit() for c in password)

Line: 12  
Problem: The docstring says "x, limited to the range from low to high", but the function returns `max(low, min(x, low))`, which incorrectly uses `min(x, low)` and then `max(low, ...)` — this results in always returning `low` if x < low, but if x > high, it incorrectly clamps to low instead of high.  
Example: clamp(10, 1, 5) returns 5, which is correct, but clamp(2, 1, 5) returns 2, which is correct — wait, actually the logic is flawed: min(x, low) when low is 1 and x is 2 gives 2, then max(1, 2) gives 2 — correct. But if x is 0, min(0,1)=0, max(1,0)=1 — correct. But if x is 10, low=1, high=5: min(10,1)=1, max(1,1)=1 — wrong, should be 5.  
Example: clamp(10, 1, 5) returns 5, but the function returns max(1, min(10,1)) = max(1,1) = 1, which is wrong.  
Fix: return max(low, min(x, high))
