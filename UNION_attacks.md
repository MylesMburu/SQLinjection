# UNION attacks

The union keyword lets you exucute one or more additional SELECT queries and append the results to the original query.

>SELECT a,b FROM table2 UNION SELECT c,d FROM table2

>This will display data in two columns: The first column having data from a,c and the second column having data from b,d

The **rules** of using UNION are:
1. The number of columns in the SELECT statements must be similar
2. The data types of the columns must be compatible

If these requirements are met, then a UNION attack can be performed.

The first step in a union attack is determining the number of columns.
We can do this by adding ** 'UNION SELECT NULL-- ** to the url query.

If you get an error, then that is not the correct number of columns. Keep adding NULL till a data column is displayed. i.e

>' UNION SELECT NULL--
>
>' UNION SELECT NULL,NULL--
>
>' UNION SELECT NULL,NULL,NULL--
>etc.
