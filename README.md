## PROJECT OVERVIEW
This project explains the importance of LOOKUP functions in data analysis, and how LOOKUP functions help with complex search or findings in a table or range by row.

# EXCEL-LOOKUP-FUNCTIONS

In Microsoft Excel, LOOKUP is a function that helps you find a value in a table or range by row or column. You can use it to search for a value in a single row or column and find a value from the same position in a second row or column.
For example, if you have a table of product prices and you want to find the price of a specific product, you can use the LOOKUP function to return the price of that product.

## EXAMPLES OF LOOKUP FUNCTIONS AND THEIR USE IN EXCEL

### VLOOKUP, HLOOKUP
This is a Microsoft Excel function also known as vertical lookup which is used to find a value in a table or range by row. It is used to search for a value in the first column of a table from the left and returns a value in the same row from a column you specify.

Syntax: =VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])
Syntax: =HLOOKUP(lookup_value, table_array, row_index_num, [range_lookup])


Here’s what each argument means:

* lookup_value: The value you want to look up.
* table_array: The range of cells that contains the data you want to search.
* col_index_num: The column number in the range that contains the data you want to return.
* range_lookup: Optional. A logical value that specifies whether you want an exact match or an approximate match. If you enter TRUE or leave this argument blank, Excel will look for an approximate match. If you enter FALSE, Excel will look for an exact match.

### XLOOKUP
XLOOKUP is a function in Microsoft Excel that helps you find things in a table or range by row. It is a more versatile and faster alternative to VLOOKUP and HLOOKUP functions.
You can use XLOOKUP to search for a value in a table or range by row or column. It can search in any direction (up, down, left, right) and can return a result from the same row or column, regardless of which side the return column is on.

The syntax for the XLOOKUP function is as follows: =XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode])

Here’s what each argument means:

* lookup_value: The value you want to look up.
* lookup_array: The range of cells that contains the data you want to search.
* return_array: The range of cells that contains the data you want to return.
* if_not_found: Optional. Where a valid match is not found, return the text you supply. If a valid match is not found, and if_not_found is missing, #N/A is returned.
* match_mode: Optional. Specify the match type:
* 0 - Exact match. If none found, return #N/A. This is the default.
* -1 - Exact match. If none found, return the next smaller item.
* 1 - Exact match. If none found, return the next larger item.
* 2 - A wildcard match where *, ?, and ~ have special meaning.
* search_mode: Optional. Specify the search mode to use:
* 1 - Perform a search starting at the first item. This is the default.
* -1 - Perform a reverse search starting at the last item.
* 2 - Perform a binary search that relies on lookup_array being sorted in ascending order. If not sorted, invalid results will be returned.
* -2 - Perform a binary search that relies on lookup_array being sorted in descending order. If not sorted, invalid results will be returned.


