# Naming Conventions

Folder names: all_lower_case_and_snake_case

File names: all_lower_case_and_snake_case

<p></p>
Class names: First_Letters_Capitalized_And_Snake_Case

* Abbreviations are allowed

<p></p>
Function names: all_lower_case_and_snake_case

* No abbreviations

<p></p>
Variable names: all_lower_case_and_snake_case

* Try to keep variable names under 15 characters, but be descriptive and exact where possible
* Single-word names are preferred<sup>[1]</sup>
* Parameter names should evoke the role of the parameter in the function, not just the kind of argument that is allowed. For example, if the variable stores a list of student names, then it could be called `student_names` instead of `lst` <sup>[1]</sup>
* Single letter parameter names are acceptable when their role is obvious, but avoid “l” (lowercase ell), “O” (capital oh), or “I” (capital i) to avoid confusion with numerals<sup>[1]</sup>
* Try to only use `i`, `j`, `k` as index names and avoid them for other uses<sup>[1]</sup>
* Avoid using built-in function names as variable names anywhere, as they break the built-in functions. For example, you should not use `sum`, `dict`, `map`, `len`, etc. as variable names.<sup>[1]</sup>

<small>[1] borrowed from [Prof. Marina Langlois at UCSD](https://dsc-courses.github.io/dsc20-2023-wi/styleguide/)</small>


<br>


# Coding
<small>(This section is borrowed from [Prof. Marina Langlois at UCSD](https://dsc-courses.github.io/dsc20-2023-wi/styleguide/))</small>

<p></p>
Try to avoid using magic numbers (i.e. any number except 0, 1, -1) directly in the `.py` files

* If you need to use, say, 17 in your code, create a variable with a meaningful name and use the variable instead
* The reason behind is that numbers have meanings. 17 might mean distance in some context and age in another context. You should define meaningful variable names to differentiate between the meanings.

When using Pandas DataFrames and any Pandas functionality, DO NOT use `inplace=True` under any circumstance.


### Commenting

<p></p>
All functions should include a method docstring (function description).

* Each docstring is surrounded by triple quotes (`"""`) instead of triple single quotes (`'''`)
* This includes any inner function and helper function
* Description should briefly describe what the method does, instead of what steps you take to achieve the result. Example:
    * Correct: Takes in a list of numbers, doubles each of them, and returns the doubled list;
    * Incorrect: Initializes an empty list and loops through the input list. For each number, I double it and append to the resulting list.

### Markdown Guide 
https://www.markdownguide.org/cheat-sheet/
