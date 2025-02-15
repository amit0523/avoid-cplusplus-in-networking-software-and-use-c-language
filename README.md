You should avoid C++ if you are developing networking software (like protocols, socket programming, etc.).

The main reasons for this are given below:

1. C++ is a complex language and very few people are expert in C++ language. If a company writes its networking software in C++ then when that person leaves then the company has to find another C++ developer and good/expert C++ developers are hard to find.

2. If you are writing networking software then you need to deal with pointers and if you are already dealing with pointers then its better to use C language.

3. C++ is slower than C, and the networking software should be fast.

4. The main advantage of C++ is Standard Template Library but it will generate new code for every data type and thus make the software slow. You can use my C library (https://github.com/amit0523/generic-doubly-linked-list-library) as any data structure (list, map, set, etc.) and speed up your development. You don't need to implement data structures from scratch, you can simply use functions in my C library to use it as any data structure. Again, my library can be found here: https://github.com/amit0523/generic-doubly-linked-list-library (Discalimer: I am not writing this article to promote my library but to make networking software fast and easy to develop).

5. I have myself worked in two projects in C++ but actually that was not true C++. They just wrote C code in C++ classes. So, they mostly just used the class feature of C++, the rest was C code. They did some operator overloading but that made code a little difficult to read. So, then why to use C++ just to write C code in C++ classes? Why not simply use C language and write C code?
