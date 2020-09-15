# bigint-optimized

Big Integer implementation with optimizations, homework from C++ Course in ITMO University, Applied Mathematics and Informatics specialization, repository with other homeworks : [cpp-repository](https://github.com/garipovroma/first-term)

---

`big_integer` implementation includes :

- Default constructor that initializes number to zero `big_integer();`
- Copy constructor, after which the original object and the copy can be modified independently `big_integer(big_integer const& other);`
- Constructor from int `big_integer(int a);`
- Explicit constructor from std :: string `explicit big_integer(std::string const& str);`
- Assignment operator `big_integer& operator=(big_integer const& other);`
- Comparison operators (`==, !=, <, >, <=, >=`)
- Arithmetic operations: addition, subtraction, sign change (unary minus), unary plus
- Multiplication running in time O (nm), where n, m are the lengths of the factors in bits
- Division and remainder of division working in time O (nm), where n is the length of the divisor in bits, and m is the length of the quotient in bits. Algorithm :  [Multiple-Length Division Revisited: A Tour of the Minefield](http://surface.syr.edu/cgi/viewcontent.cgi?article=1162&context=eecs_techreports)
- Prefix / postfix increment / decrement (`++x, x++, x--`)
- Bitwise operations: and, or, exclusive or, not (`&, |, ^, ~`)
- Bit shifts (`x >> y, x << y, x >>= y, x <<= y`)
- `std::string to_string(big_integer const&)` function
- Big Integer digits recorded in special [storage](https://github.com/garipovroma/bigint-optimized/blob/master/big_integer/storage.h) in `uint32_t` type and all bits of storage are used for big int representation

**Optimizations :**

- Small Object Optimization(Small String Optimization(SSO)): [CppCon 2016: Nicholas Ormrod “The strange details of std::string at Facebook"](https://blogs.msmvps.com/gdicanio/2016/11/17/the-small-string-optimization/), [short article about SSO](https://blogs.msmvps.com/gdicanio/2016/11/17/the-small-string-optimization/)

- Copy on Write Optimization(CoW optimization) : [wikipedia-page](https://en.wikipedia.org/wiki/Copy-on-write) 

  