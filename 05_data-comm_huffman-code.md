

## Homework (due date: 10/2)
2. Consider following symbols, compute __a)__ the Huffman code, __b)__ draw the code tree, __c)__ the average code length, and __d)__ the entropy of the code. <br>
{(A, 0.25), (B, 0.25), (C, 0.125), (D, 0.125), (E, 0.125), (F, 0.0625), (G, 0.0625)}

p_ = {0.25, 0.25, 0.125, 0.125, 0.125, 0.0625, 0.0625}
 
 |title|_s<sub>1</sub>_|_s<sub>2</sub>_|_s<sub>3</sub>_|_s<sub>4</sub>_|_s<sub>5</sub>_|_s<sub>6</sub>_|_s<sub>7</sub>_|
 |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
 |_p(x)l(x)_| 0.5 | 0.5 | 0.375 | 0.375 | 0.375 | 0.25 | 0.25 |
 |_l(x)_| 2 | 2 | 3 | 3 | 3 | 4 | 4 |
 |_c(x)_| 00 | 01 | 100 | 101 | 110 | 1000 | 1001 |
 |_p(x)_| 0.25 | 0.25 | 0.125| 0.125 | 0.125 | 0.0625 | 0.0625 |
 |      |    0\ | /1    |    0\ | /1     |       |      0\ | /1      |
 |      |  0.5 |      | 0.25 |       |       |  0.125 |        |
 |      |      |      |      |       |     0\ | /1      |        |
 |      |      |      |      |       | 0.25  |        |        |
 |      |      |      |    0\ |       | /1     |        |        |
 |      |      |      |  0.5 |       |       |        |        |
 |      |    0\ |      | /1    |       |       |        |        |
 |      |    1 |      |      |       |       |        |        |
 
 ___L = &Sigma;{_i_=1:_N_} _p<sub>i</sub>l<sub>i</sub>____
 
 =  0.5+ 0.5+ 0.375+ 0.375+ 0.375+ 0.25+ 0.25= 2.625 bits.
 
 ___H = &Sigma;{_i_=1:_N_} _p<sub>i</sub>log<sub>2</sub>(1/p<sub>i</sub>)____
 
 =  0.25x2+ 0.25x2+ 0.125x3+ 0.125x3+ 0.125x3+ 0.0625x4+ 0.0625x4= 2.625 bits.
 
 ___H &le; L < H+1___

## Program Project (due date: 10/16)
- Use any programming language you like to output the Huffman code of Homework 2.
    - Input: {(A, 0.25), (B, 0.25), (C, 0.125), (D, 0.125), (E, 0.125), (F, 0.0625), (G, 0.0625)}
    - Output: The Huffman code for each symboles.
- Bonus 1: Draw the code tree.
- Bonus 2: A general purpose version of Huffman code generater, i.e. user can input a finite set of symbols and their probabilities, then output their Huffman codes.
- Your work have to submit to your github which includes source code, outputs and a brief of your ideas in README.
