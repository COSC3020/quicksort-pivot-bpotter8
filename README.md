[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

Answer:

To calculate the probability of selecting a good pivot with the median-of-three strategy, we can separate the array in a way that the elements in the lower range are "L", the elements in the middle range are "M", and the elements in the upper range are "U".

"L" is responsible for $\frac {1} {4}$ of the elements.

"M" is responsible for $\frac {1} {2}$ of the elements.

"U" is responsible for $\frac {1} {4}$ of the elements.

The possible permutations leading to a bad pivot are LLL, UUU, LLU, UUL, ULL, LUU, LUL, ULU, MLL, LLM, UUM, MUU, UMU, and LML.

Because of no "M", the following have a probability of ($\frac {1} {4} \cdot \frac {1} {4} \cdot \frac {1} {4}$) each: LLL, UUU, LLU, UUL, ULL, LUU, LUL, and ULU.

Because of only one "M", the following have a probability of ($\frac {1} {4} \cdot \frac {1} {4} \cdot \frac {1} {2}$) each: MLL, LLM, UUM, MUU, UMU, and LML.

So, $\frac {1} {64} (8) = \frac {8} {64}$ and $\frac {1} {32} (6) = \frac {12} {64}$. 

$\frac {8} {64} + \frac {12} {64} = \frac {20} {64}$.

The probability of getting a good pivot would be $\frac {64} {64} - \frac {20} {64} = \frac {44} {64} =$ 68.75%.

The method of median-of-three has a higher probability of choosing a good pivot with 68.75% when compared to simply choosing the first element with 50%.
