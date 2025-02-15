You should avoid C++ if you are developing networking software (like protocols, socket programming, etc.).

The main reasons for this are given below:

1. C++ is a complex language and very few people are expert in C++ language. If a company writes its networking software in C++ then when that person leaves then the company has to find another C++ developer and good/expert C++ developers are hard to find.

2. If you are writing networking software then you need to deal with pointers and if you are already dealing with pointers then its better to use C language.

3. C++ is slower than C, and in networking the software should be fast.

4. The main advantage of C++ is Standard Template Library but it will generate new code for every data type and thus make the software slow. You can use my C library (https://github.com/amit0523/generic-doubly-linked-list-library) as any data structure (list, map, set, etc.) and speed up your development. You don't need to implement data structures from scratch, you can simply use functions in my C library to use it as any data structure. Again, my library can be found here: https://github.com/amit0523/generic-doubly-linked-list-library (Discalimer: I am not writing this article to promote my library but to make networking software fast and easy to develop).
