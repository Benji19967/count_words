# Counting frequency of each word in a file

Answer all questions mentioned here:
https://benhoyt.com/writings/count-words/

- [x] What about capitalization? 

Convert words to lowercase before adding them to a HashMap.

- [x] Punctuation? 

Remove all punctuation. 

- [ ] What is the time complexity of `s.replace(...)`?

- [x] How does it order two words with the same frequency?

The order is random if we just sort by count. The output may be different for
different runs on even on the same input. 

- [ ] What’s the performance bottleneck likely to be?
- [x] How does it fare in terms of big-O?

Assuming `n` is the number of words and `m` the length of the longest word.

  - [x] Getting the frequency of all words

O(n * m): iterate over each word O(n) and add to HashMap O(1 * m).

  - [x] Getting the frequency of the most common k words

O(k * (n log n)): Sorting is O(n log n) and comparing any two words is O(k)

- [ ] What’s the memory usage?
- [ ] Roughly how long would your program take to process a 1GB file?
- [ ] Would your solution still work for 1TB?
- [ ] Or you can take it in a “software engineering” direction and talk about error handling, testability, turning it into a hardened command line utility, etc.
