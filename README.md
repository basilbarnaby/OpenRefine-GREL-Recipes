# OpenRefine GREL Recipes
A compilation of OpenRefine GREL Recipes for manipulating data.

## Dates and Conversions
#### Sat Jan 09 05:00:00 EST 1982 to MySQL dateTime format
> value.slice(8, 10) + "/01/" + value.slice(24, 30)

#### ISO 8601 (TZ) date format to MySQL dateTime format
> value.slice(0, 10) + " 00:00:00"

#### MySQL Current Date format
> now().slice(0, 10) + " 00:00:00"

#### Date difference
> diff(date 1, date 2, 'format')

Returns the difference between 'date 1' and 'date 2' in the format (months, days, etc.) specified

## String manipulation
#### String replace
> value.replace("str1", "str2")  

The first parameter is what searched for and the second parameter is what the first parameter is replaced with.

> value.replace(' ','')

Replaces blank spaces with no space.

> value.replace("''"," ")

Replaces quotations with blank space (NOTE: double quotations must be used on the outside.)

#### Convert number to string with No Scientific Notation
> value.floor().toString()

#### Getting the value of a cell
> cells["Column1"].value

The array contains the name of the source cell and "value" is its value 

#### Concatenating cells
> cells['Column1'].value + cells['Column2'].value

#### Concatenates a string to a specified column
> cells['Column1'].value + 'str1'

#### Returns first character of a string
> value.splitByCharType[0]

Returns the first element of a string based on the character type

## Comparisons - returns true or false
#### Compare the values of two columns
> value. == cells['Column1'].value


#### String contains
> value.contains('str1')

Checks if the value contains "str1"

#### String starts with
> value.startsWith('str1')

Checks if the value starts with "str1"

#### String ends with
> value.endsWith('str1')

Checks if the value ends with "str1"

