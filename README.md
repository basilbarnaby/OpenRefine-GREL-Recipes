# OpenRefine GREL Recipes
A compilation of OpenRefine GREL Recipes for manipulating data.

## Date conversions
#### Sat Jan 09 05:00:00 EST 1982 to MySQL dateTime format
> value.slice(8, 10) + "/01/" + value.slice(24, 30)

#### ISO 8601 (TZ) date format to MySQL dateTime format
> value.slice(0, 10) + " 00:00:00"

#### Current Date
> now().slice(0, 10) + " 00:00:00"

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
