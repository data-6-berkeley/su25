---
layout: page
title: Exam Cheat Sheet
tagline: Cheat sheet for quizzes and exams
nav_exclude: true
---

# Data 6 Python Cheat Sheet
_This cheat sheet has been modified from the Data 6 Python Reference and includes all of the functions and table methods that you will need for the exams._

## Built-In Python Functions

| **Function** | **Description** | **Input** | **Output** |
| `str(val)` | Converts `val` to a string | A value of any type (**int**, **float**, **NoneType**, etc.) | The value as a **string** |
| `int(num)` | Converts `num` to an int | A numerical value (represented as a **string** or **float**) | The value as an **int** |
| `float(num)` | Converts `num` to a float | A numerical value (represented as a **string** or **int**) | The value as a **float** |
| `len(arr)` | Returns the length of `arr` | **array** or **list** | **int**: the length of the array or list |
| `max(arr)` | Returns the maximum value in `arr` | **array** or **list** | The maximum value the array (usually an **int**) |
| `min(arr)` | Returns the minimum value in `arr` | **array** or **list** | The minimum value the array (usually an **int**) |
| `sum(arr)` | Returns the sum of the values in `arr` | **array** or **list** | **int** or **float**: the sum of the values in the array |
| `abs(num)` | Returns the absolute value of `num` | **int** or **float** | **int** or **float** |
| `print(input, ...)` | Prints the `input`. Multiple inputs can be passed, and they will be separated by spaces by default. | **input**: any inputs to print <br>| **None**|
| `type(object)` | Returns the type of `object`. | **object**: the object whose type is to be determined | **type**: the type of the object|


## NumPy Array Functions

| **Function** | **Description** | **Input** | **Output** |
| `make_array(val1, val2, ...)` | Makes a NumPy array with the inputted values | A sequence of values | An **array** with those values |
| `np.mean(arr)` or `np.average(arr)` | Calculates the average value of `arr` | An **array** of numbers | **float**: The average of the array |
| `np.sum(arr)` | Returns the sum of the values in `arr` | **array** | **int** or **float**: the sum of the values in the array |
| `np.prod(arr)` | Returns the product of the values in `arr` | **array** | **int** or **float**: the product of the values in the array |
| `np.sqrt(num)` | Calculates the square root of `num` | **int** or **float** | **float** : the square root of the number |
| `np.arange(stop)`, `np.arange(start, stop)`, or `np.arange(start, stop, step)` | Creates an array of sequential numbers starting at `start`, going up in increments of `step`, and going up to but excluding `stop`. Default `start` is 0, default `step` is 1 | **int** or **float** | **array** |
| `np.count_nonzero(arr)` | Returns the number of non-zero (or `True`) elements in an array | An **array** of values |  **int**: the number of non-zero values in `arr` |
| `np.append(arr, item)` | Appends `item` to the end of `arr`. Does not modify the original array. | 1. **array** to append to <br> 2. item to append (any type) | **array**: a new array with the appended item |
| `np.cumsum(arr)` | Returns the cumulative sum of the elements in `arr`, where each element is the sum of all preceding elements including itself | **array** | **array**: the cumulative sum of the values in the array |
| `np.diff(arr)` | Computes the difference between consecutive elements in `arr`. | **array** | **array**: the differences between consecutive elements in the array containing `len(arr) - 1` elements |



## String Methods

| **Function** | **Description** | **Input** | **Output** |
| `str.split(separator, maxsplit)` | Splits `str` into a list of substrings using the specified `separator`. If `separator` is not provided, splits at any whitespace. You can also use the optional argument `maxsplit` to limit the number of splits. | 1. (Optional) **separator**: the delimiter used to split `str` <br> 2. (Optional) **maxsplit**: maximum number of splits | **list** of substrings |
| `str.join(iterable)` | Concatenates the elements in `iterable` (usually a list or array) into a single string, with each element separated by `str`. | **iterable**: an iterable of strings to join (can be an array or list of strings) | **string**: a single string formed by joining the elements of `iterable` with the separator `str` |
| `str.replace(old, new)` | Returns a copy of the string with all occurrences of the substring `old` replaced by `new`.| `old`: the substring to be replaced. <br> `new`: the substring to replace `old` with. | string: a new string where occurrences of `old` have been replaced by `new`.|



## Tables and Table Methods

| **Function** | **Description** | **Input** | **Output** |
| `Table()` | Creates an empty table, usually to extend with data | None | An empty **Table** |
| `Table().read_table(filename)` | Create a table from a data file | **string**: the name of the file | | 
| `tbl.with_column(name, values)` or `tbl.with_columns(n1, v1, n2, v2, ...)` | Adds an extra column onto `tbl` with the label `name` and `values` as the column values | 1. **string**: name of the new column <br> 2. **array**: values in the column | **Table**: a copy of the original table with the new column(s) |
| `tbl.column(col)` | Returns the values in a column in `tbl` | **string** or **int**: the column name or index | **array**: the values in that column |
| `tbl.num_rows` | Compute the number of rows in `tbl` | None | **int**: the number of rows in the table |
| `tbl.num_columns` | Compute the number of columns in `tbl` | None | **int**: the number of columns in the table |
| `tbl.labels` | Returns the labels in `tbl` | None | **array**: the names of each column as strings |
| `tbl.select(col1, col2, ...)` | Creates a copy of `tbl` only with the selected columns | **string** or **int**: the column name(s) or index(es) to be included in the table | **Table** with the selected columns |
| `tbl.drop(col1, col2, ...)` | Creates a copy of `tbl` without the selected columns | **string** or **int**: the column name(s) or index(es) to be dropped from the table | **Table** without the selected columns |
| `tbl.relabeled(old_label, new_label)` | Creates a new table, changing the column name specified by `old_label` to `new_label`, and leaves the original table unchanged. | 1. **string**: the old column name <br> 2. **string** the new column name | **Table**: a copy of the original table with the changed column name |
| `tbl.show(n)` | Displays the first `n` rows of `tbl`. If no argument is specified, the function defaults to showing the entire table | (Optional) **int**: number of rows to be displayed | None (table is displayed) |
| `tbl.sort(column_name)` | Sorts the rows of `tbl` by the values in the `column_name` column. Defaults to ascending order unless the optional argument `descending=True` is included. | 1. **string** or **int**: name or index of the column to sort <br> 2. (Optional) `descending=True` | **Table**: a copy of the original table with the column sorted |
| `tbl.where(column, predicate)` | Creates a copy of `tbl` containing only the rows where the value of `column` matches the `predicate`. See `Table.where` predicates below. | 1. **string** or **int**: column name or index <br> 2. `are.(...)` predicate | **Table**: a copy of the original table with only the rows that match the predicate |
| `tbl.take(row_indices)` | Creates a table with only the rows at the given indices. `row_indices` is either an array of indices or an integer corresponding to one index. | **int** or **array**: indices of rows to be included in the table | **Table**: a copy of the original table with only the rows at the given indices |
| `tbl.apply(function)` or `tbl.apply(function, col1, col2, ...)` | Returns an **array** of values resulting from applying a function to each item in a column. | 1. **Function**: function to apply to column <br> 2. (Optional) **string** or **int**: the column name(s) or index(es) to apply the function to | **array** containing an element for each value in the original column after applying the function to it |
| `tbl.group(column_or_columns, function)` | Groups rows in `tbl` by unique values or combinations of values in a column(s). Multiple columns must be entered as an array of strings. Values in the other columns are aggregated by count (by default) or the optional argument `function`. You can visualize the `group` function [here](http://data8.org/interactive_table_functions/). | 1. **string** or **array of strings**: column(s) on which to group <br> 2. (Optional) **Function**: function to aggregate values in cells (defaults to counting rows) | **Table** a new groupped table |
| `tbl.pivot(col1, col2)` or `tbl.pivot(col1, col2, values, collect)` | Creates a pivot table where each unique value in `col1` has its own column and each unique value in `col2` has its own row. Counts or aggregates values from a third column, collected with some function. If the `values` and `collect` arguments are not included, `pivot` defaults to returning counts in the cells. You can visualize the `pivot` function [here](http://data8.org/interactive_table_functions/). | 1. **string**: name of the column in `tbl` whose unique values will make up the columns of the pivot table <br> 2. **string**: name of column in `tbl` whose unique values will make up the rows of the pivot table <br> 3. (Optional) **string**: name of the column in `tbl` that describes the values of cells in the pivot table <br> 4. (Optional) **Function**: how the values are collected (e.g. `sum` or `np.mean`) | **Table**: a new pivot table |
| `tblA.join(colA, tblB)` or `tblA.join(colA, tblB, colB)` | Generate a table with the columns of `tblA` and `tblB`, containing rows for all values in `colA` and `colB` that appear in `tblA` and `tblB`, respectively. By default, `colB` is the same value as `colA`. `colA` and `colB` must be strings specifying column names. | 1. **string**: name of column in `tblA` with values to join on <br> 2. **Table**: the other table <br> 3. (Optional) **string**: the name of the shared column in `tblB`, if column names are different between the tables | **Table**: a new combined table |
| `tbl.with_row(values)` | Adds a new row with the specified `values` to `tbl` | 1. **list** or **array**: values to add as a new row | **Table**: a copy of the original table with the new row |
| `tbl.with_rows(list_of_rows)` | Adds multiple rows to `tbl` using a list of rows | 1. **list** of **lists** or **arrays**: each list/array represents a new row | **Table**: a copy of the original table with the new rows |

## Visualization Functions

| **Function** | **Description** | **Input** | **Output** |
| `tbl.barh(categories)` or `tbl.barh(categories, values)` | Displays a horizontal bar chart with bars for each category in the column `categories`. `values` specifies the column corresponding to the size of each bar, but is unnecessary if the table only has two columns. Optional argument `overlay` (default is `True`) specifies whether grouped bar charts should be overlaid or on separate plots. | 1. **string**: name of the column with categories <br> 2. (Optional) **string**: name of the column with values corresponding to the categories | None: draws a bar chart |
| `tbl.hist(column)` | Generates a histogram of the numerical values in `column`. Optional arguments `group` (to specify categorical column to group on), `bins` (to specify custom bins), and `overlay` to specify overlaid or separate histograms. | **string**: name of the column | None: draws a histogram |
| `tbl.plot(x_column, y_column)` or `tbl.plot(x_column)` | Draws a line plot consisting of one point for each row in `tbl`. If only `x_column` is specified, `plot` will plot the rest of the columns on the y-axis with different colored lines. Optional argument `overlay` (default is `True`) specifies whether multiple lines should be overlaid or on separate plots. | 1. **string**: name of the column on the x-axis <br> 2. **string**: name of the column on the y-axis | None: draws a line graph |
| `tbl.scatter(x_column, y_column)` | Draws a scatter plot consisting of one point for each row in `tbl`. The optional argument `fit_line=True` can be included to draw a line of best fit through the scatter plot. The optional arguments `group` (to specify categorical column to group on) and `sizes` (to specify a numerical column for bubble sizes) can also be used to encode additional variables. | 1. **string**: name of the column on the x-axis <br> 2. **string**: name of the column on the y-axis <br> 3. (Optional) `fit_line=True` | None: draws a scatter plot |

## Table.where Predicates
These functions can be passed in as the second argument to `tbl.where(..)` and act as a condition by which to select rows from `tbl`.

| **Predicate** | **Description** |
| `are.equal_to(Z)` |	Equal to `Z` (can be an **int**, **float** or **string**) |
| `are.not_equal_to(Z)`	| Not equal to 'Z' can be a number (**int** or **float**) or a **string**) |
| `are.above(x)`	| Greater than `x` |
| `are.above_or_equal_to(x)` | Greater than or equal to `x` |
| `are.below(x)`	| Less than `x` |
| `are.below_or_equal_to(x)` |	Less than or equal to `x` |
| `are.between(x,y)` |	Greater than or equal to `x` and less than `y` |
| `are.between_or_equal_to(x,y)` |	Greater than or equal to `x`, and less than or equal to `y` |
|  `are.strictly_between(x,y)` |	Greater than `x` and less than `y` |
| `are.contained_in(A)` |	True if it is a substring of `A  (if `A` is a **string**) or an element of `A` (if `A` is an **array**) |
| `are.containing(S)` |	Contains the string `S` |
