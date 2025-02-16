You should avoid C++ if you are developing networking software (like protocols, socket programming, etc.).

The main reasons for this are given below:

1. C++ is a complex language and very few people are experts in C++ language. If a company writes its networking software in C++ then when that person leaves then the company has to find another C++ developer and good/expert C++ developers are hard to find.

2. If you are writing networking software then you need to deal with pointers and if you are already dealing with pointers then it is better to use C language.

3. C++ is slower than C, and the networking software should be fast, so the networking software should be written in C.

4. One advantage of C++ is Standard Template Library but it will generate new code for every data type and thus make the software slow. You can use my C library (https://github.com/amit0523/generic-doubly-linked-list-library) as any data structure (list, map, set, etc.) and speed up your development. You don't need to implement data structures from scratch, you can simply use functions in my C library to use it as any data structure. Again, my library can be found here: https://github.com/amit0523/generic-doubly-linked-list-library (Disclaimer: I am not writing this article to promote my library but to make networking software fast and easy to develop).

5. I have worked on two projects in C++ but, actually, that was not true C++. They just wrote C code in C++ classes. So, they mostly just used the class feature of C++, the rest was C code. They did some operator overloading but that made the code a little difficult to read. So, then why to use C++ just to write C code in C++ classes? Why not simply use C language and write C code?

6. There is no need of C++ string class in networking software because in networking software, we deal with bytes and not strings.

7. Now, C++ supporters will say that code can be managed better in C++ because the code and the data live together in a class. Even C code can be managed well. Linux kernel has around 30 million lines of code and it is all in C and it is managed well. So, large C code bases can be managed well. I have mostly worked in the networking domain and I have used only C (and no C++) and the total lines of code were in hundreds of thousands, even then the code base was managed well. In a company, it is not that any developer can write/change any code and check it in, first the code has to go through reviews (by 3-4 peer developers and the team lead) and then some testing and only then it will be allowed to be checked in, so C code base can be managed well.

8. There is no need (or not much need) of handling files in networking software.

9. Operator overloading in C++ makes code difficult to read, so it should be avoided.

10. Multiple inheritance should be avoided because it makes code complex. Code reuse can be done in C also.

11. If you want to make your variable/function private in C (just like by using private keyword in C++) then you can declare your variable/function as static and then that variable/function will not be visible outside of that file.

12. C++ has a big security hole. You can change the values of private member variables directly by getting the pointer to the object. So, private member variables are actually not private. There is no point in picking C++ over C from the security point of view. Below is the example code:
```

#include <iostream>

using namespace std;

class MyClass
{

private:
    int i;
    int j;

public:
    MyClass(int a, int b)
    {
        i = a;
        j = b;
    }

    void print_data()
    {
        cout << endl;
        cout << "i = " << i << ", j = " << j;
    }

}; // end of class MyClass

int main(void)
{

    MyClass myobj(1, 4);

    myobj.print_data();

    MyClass *m = &myobj;
    
    int *i_ptr = (int *)(m);
    int *j_ptr = i_ptr + 1;

    *i_ptr = 10;
    *j_ptr = 20;

    myobj.print_data();

    cout << endl << endl;

    return 0;

} // end of function main()

The output is:

i = 1, j = 4
i = 10, j = 20

So, you see that the private member variables values were changed directly using pointers.
So, C++ is not a secure language. Although, C is also not a secure language but there is no point
in picking C++ over C from the security point of view.

```

13. In most of the networking software multi-threading is required. Posix threads in C are easy to use. I detach the thread after creating it by using pthread_detach() so that I don't have to do pthread_join().

14. So, actually there is not enough reason to use C++ in networking software. In networking software, most of the features of C++ are not used. The only feature that's used is the C++ class to wrap the C code. But then there is no point in using C++. C code base can be managed well by having reviews of code by 3-4 peer developers and the team lead and then some testing before it is checked in.

15. So, my opinion is that networking software should not be written in C++ but it should be written in C.
