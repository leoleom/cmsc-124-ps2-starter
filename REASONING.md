# Reasoning Before Execution

Write the rule behind each case before you commit your predictions. Replace
every placeholder line below with one to three sentences that name the rule
producing that case's value, type, length, and dimensions. One rule is enough.
After you run and find a miss, add a short correction entry under that case in a
later commit.

## P01
R converts to the highest type and with 3.5 it is double. Additionally, TRUE is converted into 1 because of type casting (wherein TRUE is 1 and False is 0) and 2L becomes 2. Value is [1,2,3.5], length 3, no dim.

## P02
Character is the most dominant of all the types, and since "2" is a string, every other element is type casted into a character. This includes 1L as "1" and TRUE as "TRUE". Value is ["1","2","TRUE"], length 3, no dim.

## P03
The two vectors are integers therefore the result stay as an integer. Since the second vector only has 2 elements, it is repeated evenly with the 4 elements of the first vector. Value is [11,22,31,42], length 4, no dim.

## P04
Subsetting positions 3 and 1, respectively, using the inner vector. This means that from the initial vector, we are only looking up third and first in that order and returning the value which is still integer since both vectors only hold integer type. Value is [third=9,first=8], length 2 with no dim.

## P05
The negative symbol in the subset means exclude so -2L removes 7 from the vector since it is the 2nd index. Therefore, the final value is [4,9], integer, length 2, no dim.

## P06
is.na(x) | x > 10L is checked against each position in the vector and the element is only taken if either side is TRUE. This is why NA and 12 are taken since it sees that the element is NA or not available and 12 is the only other element that is accepted by the left condition. Thus, the value is [NA,12], integer, length 2, no dim.

## P07
Since a factor is stored as integer codes with level labels (which are low and high), so its type would result to an integer. The case sets levels = c("low", "high"), so low is code 1 and high is code 2, and it would store as 1,2,1 with the levels in that given order. Overall, the value is factor[low,high,low];levels=[low,high], length 3, no dim.

## P08
Lists in R can hold different types in separate elements, so scores stays integer and label stays a string. Value is list{scores=[3,5],label=["A"]}, list type with length 2 (two elements which are score and label), no dim.

## P09
A data frame is basically a list of equal-length columns, so its type says list not a data.frame. Its length counts columns, not rows, so it's 2 (id and passed) and because it has 2 rows and 2 columns, its dim is 2x2. Value is data.frame[2x2]{id=[1,2],passed=[TRUE,FALSE]}, with id staying integer from 1:2 and passed staying logical.

## P10
R stores a matrix by columns so 1:6 is stored as 1,2,3,4,5,6 and adding the vector c(10, 20) repeats down in that order, recycles, so 10 goes to the top row and 20 to the bottom row. Since 10 and 20 are doubles, the whole matrix becomes double. Overall, the value is matrix[2x3](11,22,13,24,15,26), length 6, dim of 2x3.

## P11
According to the manual, any operation on an NA results in a NA since if an input is incomplete the result cannot be known. mean() has to use the NA, with other elements in the type double, and since there is no na.rm to remove it, the result would be NA as well. Value is NA, double, length 1, no dim.

## P12
Unlike the previous prediction, this one passes na.rm = TRUE so mean() removes the missing value first, as the assignment says na.rm is for. That leaves 8 and 10, and their mean is 9. Therefore, the value is 9, double type with length 1 and no dim. 

## P13
This is a mixed-mode assignment where the vector has one type (initially an integer vector), however, putting the double 2.5 into the second index widens the whole vector to double, including the 1 and 3. Thus, the value is [1,2.5,3], double type, length 3, no dim.

## P14
ifelse() makes one choice per position in the vector so the NA_real_ position gets 0 and the rest get scores * 2, giving 14, 0, 24, 8. The logical index then adjusts > 15 and in this case selects only the 24, which is replaced with 15. Everything stays double. Value is [14,0,15,8], length 4, no dim.

## P15
As per the manual, an array is a vector with a dim attribute, so array(1:8, dim = c(2L, 2L, 2L)) keeps the type of 1:8, which is integer. The dimension specified 2x2x2 then gives 2 * 2 * 2 = 8 cells, and R fills them one column at a time so the values stay in the order 1 to 8. The result comes to array[2x2x2](1,2,3,4,5,6,7,8) where the type is an integer, length is 8, and dimension is a 3-dimensional 2x2x2.

## P16
c(4L, 7L, 9L)[0L] specifically indexes 0 which is not possible since R uses 1-based indexing. The rule also stated that index 0 selects nothing, thus the result is an empty integer vector. Overall, value is [], integer type with length 0, no dim.