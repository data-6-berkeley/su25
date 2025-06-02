---
layout: page
title: Python Reference
description: >-
    Python Reference Guide
---

# Python Reference &#x1F40D;
{:.no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Understanding the Python Reference

If you're new to reading documentation, looking at the Data 6 Python Reference might feel a little overwhelming, but don't worry — the point of this class is *not* to memorize all of these functions or their arguments. For exams and quizzes, you will be provided with a reference sheet that contains all of the functions you may need on the exam.

However, we do expect you to understand how to use the Python Reference to understand new functions, and to help with debugging when things go wrong. Learning how to read and understand documentation is a key to becoming a good data scientist. In fact, even course staff continue to use the Python Reference to refresh their memory about certain functions.

Of course, the Python Reference can only provide information about the basics of the functions you'll use in Data 6. The best knowledge about functions comes from using these functions in code you write in labs or homeworks. If you get stuck when using a certain function, we encourage you to come to office hours or ask a question on [Ed](https://edstem.org/us/courses/60192/).

### The Anatomy of a Function

<div class="code_block">
<span class="control">def</span> <span class="func">my_function</span>(num):<br>
    <span class="indent"><span class="control">return</span> num <span class="op">**</span> <span class="num">3</span></span>
</div>

In the function above, `my_function` is the name of the function, which takes one argument called `num`. The data type of the input is an **int** or **float**, and the function returns the number raised to the power 3, which is also an **int** or **float**.

### How to Read These Tables

* The **Function** column tells you how to call the function and what arguments it accepts. Everything written in `this font` is code or refers to a particular argument in the function (e.g. `num` in `np.sqrt(num)`).
* The **Description** column gives you a brief description of what the function does, including what each argument is used for
* The **Input** column tells you what data type each argument needs to be. If you're getting a `TypeError`, it might be because your inputs are of the wrong type. Data types are indicated in bold (e.g. **string** or **Table**).
* The **Output** column tells you what the function returns and what data type it is.

<hr>

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


## More Documentation

The Data 6 Python reference guide is based on the Data 8 [Python Reference](https://www.data8.org/sp25/reference/). More detailed Python documentation is available [here](https://docs.python.org/3/).
