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
Replace this line with the rule that decides this case.

## P09
Replace this line with the rule that decides this case.

## P10
Replace this line with the rule that decides this case.

## P11
Given theres a missing value, finding the mean will yield NA aswell as it needs a definite values for each. Type is double as Real = Double. Plain vector so no dim

## P12
A more defined version of P11 here we effectively remove NA values so we can proceed and apply the mean function and yield a defined value. Type is Double and vector is plain so no dim

## P13
Replace this line with the rule that decides this case.

## P14
Replace this line with the rule that decides this case.

## P15
Replace this line with the rule that decides this case.

## P16
Replace this line with the rule that decides this case.
