# Counting frequency of each word in a file

## Profiling

`cargo flamegraph --root -- --path <input-file>` (`dtrace` on MacOS requires `--root`)

`open flamegraph.svg`

## Questions one could ask during an interview

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

O(m * (n log n)): Sorting is O(n log n) and comparing any two words is O(m)

- [x] What’s the memory usage?

Topped out at 1.1MB when processing a 1.3GB file.

- [x] Roughly how long would your program take to process a 1GB file?

Took around 35 seconds on a 1.3GB file on a MacBook Pro M1 2020.

- [ ] Would your solution still work for 1TB?
- [ ] Or you can take it in a “software engineering” direction and talk about error handling, testability, turning it into a hardened command line utility, etc.
