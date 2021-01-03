# biginteger
C++ implementation of big integer class:
* Default constructor that initializes number to zero.
* Copy constructor, after which the original object and the copy can be modified independently.
* Constructor from `int`.
* Explicit constructor from `std::string`.
* Assignment operator.
* Comparison operators.
* Arithmetic operations: addition, subtraction, sign change (unary minus), unary plus.
* Multiplication running in `O(nm)` time, where `n`, `m` are the lengths of the factors in bits.
* Division and remainder of division working in time `O(nm)`, where `n` is the length of the divisor in bits, and `m` is the length of the quotient in bits.
  * [There's a great article about division](http://surface.syr.edu/cgi/viewcontent.cgi?article=1162&context=eecs_techreports).
* Prefix/postfix increment/decrement.
* Bitwise operations: and, or, exclusive or, not.
* Bit shifts.
* There is a global function `std::string to_string (big_integer const &)` that returns the string representation of a number.

The implementation used optimizations:
1. _copy-on-write-optimization_ - big integer makes lazy copy of other big integer to avoid redundant data copying when it's not necessary.
2. _small-object-optimization_ - small numbers allocate no more than 1 block of heap.
