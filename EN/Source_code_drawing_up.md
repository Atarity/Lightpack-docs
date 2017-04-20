## Drawing up the source code

This document is brought to pinpoint the rules of code's drawing up, in order to keep its unified style and to raise its readability. 

- Instead of tabulation, 4 blank spaces are used for indentation in the code.

- The end of line is assigned in unix format(LF).

- In case the file contains a class definition, it is to be named as following: `%ClassName%.hpp` `%ClassName%.cpp`. Elsewise, all letters in the file name have to be lower case (small):
<pre>
SpeedTest.hpp
SpeedTest.cpp
version.hpp
</pre>

- All values start with lower case letter:
<pre>
QString filePath;
</pre>

- All function names also start with lower case letter:
<pre>
const QString & getFilePath();
</pre>

- Global values are named with the prefix `g%varName%` :
<pre>
int gDebugLevel;
</pre>

- Class values are named with the prefix `_%varName%`:
<pre>
uint8_t _buff;
</pre>

- Classes names start with upper case (capital) letter:
<pre>
class Man
{
public:
        Man();
private:
        int _height;
        int _age;
}
</pre>

- Name spaces are written in lower case characters:
<pre>
namespace lightpack
{
}
</pre>

- Constants are named starting with upper case letter with the prefix k:
<pre>
const int kFirstLetterCapital;
</pre> 

- Using #define in C++ code is not recommended. In case of a pressing need in name, all symbols must be upper case:
<pre>
# define ALL_CAPITAL_LETTERS
</pre>

- Gaps after if, for, while, and other key words:
<pre>
if (first == second)
{
    for (int i = 0; i &lt; N; i++)
        doSomething();
    while (condition)
        doSomethingElse();
} else {
    findCallbackFunction();
}

</pre>

- In case of a single statement in all branches, round brackets can be dropped:
<pre>
if (first == third)
        start();
else
        stop();
</pre>

- In header files the control directive should be used in order to eliminate collisions: 
<pre>
# pragma once
</pre>

- Name spaces are written down without gaps:
<pre>
namespace lightpack
{
namespace speedtests
{
        class AnotherMan
        {
        }
}
}
</pre> 

- When using comments with TODO markup in the code, it's desirable to describe precise author's intentions:
<pre>
int getAvgColor()
{
        // TODO: come up with a very fast algorithm for calculating the average color
        return -1;
}
</pre> 
