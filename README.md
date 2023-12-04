## PROJECT OVERVIEW
This project explains the use of LOOKUP functions in data analysis, and how LOOKUP functions help with complex search or findings in a table or range by row.

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

### QUESTIONS AND SOLUTIONS
Q1. Find the amount commissioned to the sales person (Harley Fritz) using VLOOKUP.
S. =VLOOKUP(H3,B3:F24,5,FALSE).

Q2. Find the amount commissioned to the sales person (Harley Fritz) using VLOOKUP.
S. =HLOOKUP(B9,C2:X6,5,FALSE).

Q3. Find the amount commissioned to the sales person (Harley Fritz) using VLOOKUP and Xlookup.
S. When VLOOKUP is applied to this table it returns (--N/A--) because the lookup value is not at the far left side of the table. The best solution to problems like this is to aplly XLLOKUP.
* The formular for  XLOOKUP is: =XLOOKUP(H8,F3:F24,E3:E24,,0).

Q3. Find the amount commissioned to  the sales person (Kenji) using Xlookup.
S. Apparently the name "Kenji" is not on the list of names so I had to write an Xlookup function that will return the word "Not on the list" if the name is not found. 
* The formular for the XLOOKUP function: =XLOOKUP(H8,F3:F24,E3:E24,"Not on the list").

Q5. Find the amount commissioned and sales amount of the sales person (Harley Fritz) using Xlookup
S. In the return array I had to select both roles containing the commission and sales amount.
* The formular for this: =XLOOKUP(H3,B3:B24,E3:F24).

Q6. Find the sales amount of the company (Nike) from the table using Xlookup.
S. The name Nike is not a stand alone name in the array so we need an Xlookup function that will return the sales amount of any company name that contains the word "Nike". 
* The formular for this must contain a wildcard because an exact match will return --N/A--: =XLOOKUP(H3&"*",B3:B14,E3:E14,,2) where the number 2 represents the wildcard function, and (H3&"*") represents the lookup value and whatever it is attached to.

Q7. Find the amount commissioned to (Harley Fritz) in the year 2000. 
S.This question contains two lookup values (Harley Fritz, 2000), we have to look for the commission of the sales person in that particular year.
In this solution we have to write an xlookup function inside an xlookup funtion so that we can get the result of both lookup values.
* The formular: =XLOOKUP(H3,B4:B25,XLOOKUP(I3,C3:F3,C4:F25)). Where H3 represents the sales person and I3 represents the year.

Q8. Find the commission recieved by the sales person (Harley Fritz) in the year 2020.
S. Apparently Harley Fritz received more than one commission in the year 2020, using any lookup function for this will only return one value instead of the entire commision received in the said year. The best solution for this problem is by using the filter function.
* The formular for the above question is: =FILTER(FILTER(C4:F25,B4:B25=H8),C3:F3=I8)


