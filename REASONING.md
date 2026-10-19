# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
Among the given atomic types 3.5 holds the highest type Rule which is double therefore all other data type are widened to Doubles aswell. Flat dimension so no dim

## P02
Same case to P01 the highest type in this set is Character therefore all the types within are typecasted to be Characters.Flat dimension so no dim

## P03
All types are Integer but here we are adding 2 unbalanced vector in terms of length, R performs recycling that reuses the values of the shorter vector to be utilized to complete the arithmetic. Flat dimension so no dim

## P04
All types are integer but has labels, we then select the indeces in 3 and 1 ( R indexing starts at 1) so we take only the values in 3rd followed by 1st. Flat dimension so no dim

## P05
All given types are Integer but unlike the P04 we used the negative index accessor. In R accessing a negative index yields all the values except the specified negative index. Flat dimension so no dim

## P06
All types are Integer where one of them has no inherent value. A logical index selects where TRUE. The mask is is.na(x) | x > 10L. For the NA element, is.na is TRUE hence it selected and x > 10 includes 12L dropping the values 5 and 3.

## P07
A factor stores integer codes plus a levels attribute. The levels c("low","high") map low→1 and high→2, so low, high, low is stored as codes 1,2,1 but displays as labels. typeof() reports the storage, which is integer (not factor or character). Length is 3 and it's a plain vector, so dim is none.

## P08
A list is a container whose elements keep their own types so scores = c(3L,5L) stays an integer vector [3,5], and label = "A" stays a character ["A"]. Unlike c(), a list does not coerce elements to a common type.length() counts top-level elements, so it's 2 (two items), not the total values inside and A list carries no dimension so no dim.

## P09
A data frame is a list of equal-length columns, so the type is a list even though it is a class data.frame. Length counts towards the columns, not the 4 cells created by the list. Columns are the id holding integers with corresponding passed holding logicals, and dim follows the data frame rows × columns, so 2x2 it is. The value is data.frame[2x2]{id=[1,2],passed=[TRUE,FALSE]}.

## P10
Given is a 6 element values divided into 2 rows resulting to 2x3 dim. It also applies an arithmetic operation with 2 elements so recycling is inevitable, repeating down the column storage order so 10 adds to positions 1,3,5 and 20 to 2,4,6. The final yield would be matrix[2x3](11,22,13,24,15,26) with type integer, length 6, and dim 2x3.

## P11
Given theres a missing value, finding the mean will yield NA aswell as it needs a definite values for each. Type is double as Real = Double. Plain vector so no dim

## P12
A more defined version of P11 here we effectively remove NA values so we can proceed and apply the mean function and yield a defined value. Type is Double and vector is plain so no dim

## P13
Putting 2.5 into slot 2 of the integer vector 1:3 forces the whole vector to widen to double, so 1 and 3 become doubles too. Value is [1,2.5,3], type double, length 3, no dim.

## P14
ifelse goes one position at a time so the NA becomes 0 and the rest double to 14, 0, 24, 8. The mask adjusted > 15 then catches only the 24 and replaces it with 15. Value is [14,0,15,8], type double, length 4, no dim.

## P15
An array is a vector with a dim attribute, and since 1:8 is integer the array stays integer. The 2x2x2 shape gives 8 cells filled in storage order so the values stay 1 to 8. Value is array2x2x2, type integer, length 8, dim 2x2x2.

## P16
Index 0 is allowed in R even though counting starts at 1, and it selects nothing. So the result is an empty vector that keeps the original type. Value is [], type integer, length 0, no dim.
