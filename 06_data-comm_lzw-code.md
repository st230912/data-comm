## Homework (due date: 10/2)
Use LZW algorithm to encode "abcabcabcabcabcabcabcabcabcabcabcabc".

Current|Next|Output|Add to dictionay|Comments|
|:---:|:---:|:---:|:---:|:---|
|a 97|b 98|a 97|ab 256|'ab' not exist, add it to table|
|b 98|c 99|b 98|bc 257|'bc' not exist, add it to table|
|c 99|a 97|c 99|ca 258|'ca' not exist, add it to table|
|a 97|b 98|-|-|'ab' exists in table, 'abc' not|
|ab 256|c 99|ab 256|abc 259|add 'abc' to table|
|c 99|a 97|-|-|'ca' exists in table, 'cab' not|
|ca 258|b 98|ca 258|cab 260|add 'cab' to table|
|b 98|c 99|-|-|'bc' exists in table, 'bca' not|
|bc 257|a 97|bc 257|bca 261|add 'bca' to table|
|a 97|b 98|-|-|'ab' exists in table, 'abc' exists too, 'abca' not|
|abc 259|a 97|abc 259|abca 262|add 'abca' in table|
|a 97|b 98|-|-|'ab' exists in table, so does 'abc' and 'abca', 'abcab' not|
|abca 262|b 98|abca 262|abcab 263|add 'abcab' in table|
|b 98|c 99|-|-|'bc' exists in table, bca' exist too, 'bcab' not|
|bca 261|b 98|bca 261|bcab 264|add 'bcab' to table|
|b 98|c 99|-|-|'bc' exist in table|
|bcab 264|c 99|bcab 264|bcabc 265|'bcabc'not exist, add it to table|
|c 99|a 97|-|-|'cab' exist in table|
|cab 260|c 99|cab 260|cabc 266|'cabc'not exist, add it to table|
|c 99|a 97|-|-|'cabc' exist in table|
|cabc 266|a 97|cabc 266|cabca 267|'cabca'not exist, add it to table|
|a 97|b 98|-|-|'abcab' exist in table|
|abcab 263|c 99|abcab 263|abcabc 268|add 'abcabc' in table|
|c 99|-|c 99|-|end|


    code: 97, 98, 99, 256, 258, 257, 259, 262, 261, 264, 260, 266, 263, 99.





