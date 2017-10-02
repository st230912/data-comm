## Question:
A message has 1000 symbols A, B, C and D which the probability of occurrence of each symbol is 1/3, 1/2, 1/12 and 1/12 respectively. <br>

|S<sub>i</sub>|P<sub>i</sub>|log<sub>2</sub>(1/P<sub>i</sub>)|
|:---:|:---:|:---:|
|A|1/3|1.58 bits|
|B|1/2|1 bit|
|C|1/12|3.58 bits|
|D|1/12|3.58 bits|

- The fixed-length encoding use 2 binary digits for each symbol, then transmit the message (1000 symbols) needs 2000 binary digits. <br>
- The entropy of these symbols is: 1/3 * 1.58 + 1/2 * 1 + 1/12 * 3.58 + 1/12 * 3.58 = 1.626 bits.

__Can we find an encoding where transmitting the message (1000 symbols) in 1626 binary digits in average?__

# Optimal Code
__Our goal of _Source Coding_ is to produce as few bits as possible__

One of the goal of communication system is efficient sharing of the communication links among different users or conversations, so the ability to send data as few bits as possible is necessary.

### Expected code length

Given _N_ symbols, with symbol _i_ occurring with probability _p<sub>i</sub>_, if we have a code in which symbol _i_ has length _l<sub>i</sub>_ in the code tree (i.e., the codeword is _l<sub>i</sub>_ bits long), then the expected length of the code, _L_, is &Sigma;{_i_=1:_N_} _p<sub>i</sub>l<sub>i</sub>_.

Shannon showed the _expected code length_ of any uniquely decodable code cannot be smaller then the _entropy, H_ of the symbols. Thus an _optimal code_ will have an _expected code length_ that matches the _entropy_ for the messages.





## Huffman Code Algorithm
1. Begin with the set of symbols __S__, put the probability __p(s)__ for each __s__ in __S__.
2. Repeat the following steps until there is only 1 symbol left in __S__:
3. Choose two members __(s<sub>i</sub>, s<sub>j</sub>)__ from __S__ which have lowest probabilities.
4. Remove the selected symbols from __S__, and create a new node of the code tree whose childen are the symbols you have removed __(s<sub>i</sub>, s<sub>j</sub>)__. Label the left sibling with code __0__, and the right sibling with code __1__.
5. Add a new symbol into __S__ that represent this new node and combine their probabilities (__p(s<sub>i</sub>) + p(s<sub>j</sub>)__).

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
