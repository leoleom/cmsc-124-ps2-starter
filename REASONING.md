# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
Among the given atomic types 3.5 holds the highest type Rule which is double therefore all other data type are widened to Doubles aswell. Flat dimension so no dim

## P02
Character is the most dominant of all the types, and since "2" is a string, every other element is type casted into a character. This includes 1L as "1" and TRUE as "TRUE". Value is ["1","2","TRUE"], length 3, no dim.

## P03
All types are Integer but here we are adding 2 unbalanced vector in terms of length, R performs recycling that reuses the values of the shorter vector to be utilized to complete the arithmetic. Flat dimension so no dim

## P04
Subsetting positions 3 and 1, respectively, using the inner vector. This means that from the initial vector, we are only looking up third and first in that order and returning the value which is still integer since both vectors only hold integer type. Value is [third=9,first=8], length 2 with no dim.

## P05
All given types are Integer but unlike the P04 we used the negative index accessor. In R accessing a negative index yields all the values except the specified negative index. Flat dimension so no dim

## P06
is.na(x) | x > 10L is checked against each position in the vector and the element is only taken if either side is TRUE. This is why NA and 12 are taken since it sees that the element is NA or not available and 12 is the only other element that is accepted by the left condition. Thus, the value is [NA,12], integer, length 2, no dim.

## P07
A factor stores integer codes plus a levels attribute. The levels c("low","high") map low→1 and high→2, so low, high, low is stored as codes 1,2,1 but displays as labels. typeof() reports the storage, which is integer (not factor or character). Length is 3 and it's a plain vector, so dim is none.

## P08
Lists in R can hold different types in separate elements, so scores stays integer and label stays a string. Value is list{scores=[3,5],label=["A"]}, list type with length 2 (two elements which are score and label), no dim.

## P09
A data frame is a list of equal-length columns, so the type is a list even though it is a class data.frame. Length counts towards the columns, not the 4 cells created by the list. Columns are the id holding integers with corresponding passed holding logicals, and dim follows the data frame rows × columns, so 2x2 it is. The value is data.frame[2x2]{id=[1,2],passed=[TRUE,FALSE]}.

## P10
R stores a matrix by columns so 1:6 is stored as 1,2,3,4,5,6 and adding the vector c(10, 20) repeats down in that order, recycles, so 10 goes to the top row and 20 to the bottom row. Since 10 and 20 are doubles, the whole matrix becomes double. Overall, the value is matrix[2x3](11,22,13,24,15,26), length 6, dim of 2x3.

## P11
Given theres a missing value, finding the mean will yield NA aswell as it needs a definite values for each. Type is double as Real = Double. Plain vector so no dim

## P12
Unlike the previous prediction, this one passes na.rm = TRUE so mean() removes the missing value first, as the assignment says na.rm is for. That leaves 8 and 10, and their mean is 9. Therefore, the value is 9, double type with length 1 and no dim.

## P13
Putting 2.5 into slot 2 of the integer vector 1:3 forces the whole vector to widen to double, so 1 and 3 become doubles too. Value is [1,2.5,3], type double, length 3, no dim.

## P14
ifelse() makes one choice per position in the vector so the NA_real_ position gets 0 and the rest get scores * 2, giving 14, 0, 24, 8. The logical index then adjusts > 15 and in this case selects only the 24, which is replaced with 15. Everything stays double. Value is [14,0,15,8], length 4, no dim.

## P15
An array is a vector with a dim attribute, and since 1:8 is integer the array stays integer. The 2x2x2 shape gives 8 cells filled in storage order so the values stay 1 to 8. Value is array2x2x2, type integer, length 8, dim 2x2x2.

## P16
c(4L, 7L, 9L)[0L] specifically indexes 0 which is not possible since R uses 1-based indexing. The rule also stated that index 0 selects nothing, thus the result is an empty integer vector. Overall, value is [], integer type with length 0, no dim.
