* <https://en.wikipedia.org/wiki/POSTNET>
* <https://www.cs.drexel.edu/~introcs/Fa12/assignments/HW4/index.html>
* <http://www.jiskha.com/>

为了快速对信件进行分类，美国联邦邮政局鼓励信件量大的公司用「条码」来代替邮编。
这种「条码」只有一行，有两种高度。下图展示的是数字 0 - 9 对应的条码。竖线表示长行，冒号表示短行。

    1	:::||
    2	::|:|
    3	::||:
    4	:|::|
    5	:|:|:
    6	:||::
    7	|:::|
    8	|::|:
    9	|:|::
    0	||:::

```
示例：	|	|:|::	:|:|:	|:::|	:::||	::||:	:|:|:	|
条码：	Frame	Digit-1	Digit-2	Digit-3	Digit-4	Digit-5	CD	Frame
95713	Bar	(9)	(5)	(7)	(1)	(3)	(5)	Bar
```
完整条码的两边分别有一个全高的边框。邮编的每一位数字都被编码成对应的「条码」。所有数字都被编码后，后边会跟着一位「校验码」，它的计算规则如下：把邮编中的所有数字相加，然后所得的和加上「校验码」必须是 10 的倍数。
举个栗子：邮编 95713 所有数字求和是 25，那么，25 加多少能得到 10 的倍数呢？对了，就是 5，你真棒！25 + ５= 30，30 就是 10 的倍数，真是不可思议，你干的太漂亮了！这个 5 就是校验码，你明白了吧！
邮编中的每一位数字，还有检验码都会通过下面的表格进行编码（注：下表只是上图的数字形式，1 表示全码，0 表示半码）:

        7	4	2	1	0
    1	0	0	0	1	1
    2	0	0	1	0	1
    3	0	0	1	1	0
    4	0	1	0	0	1
    5	0	1	0	1	0
    6	0	1	1	0	0
    7	1	0	0	0	1
    8	1	0	0	1	0
    9	1	0	1	0	0
    0	1	1	0	0	0

注意每一行都是两个全码和三个半码。从条码倒推数字也非常简单，根据每列的权重来就行了：7，4， 2， 1， 0。
来，举个栗子：6 的条码是：01100，所以如果我们要倒推它，只要一个公式即可：`0*7  +  1*4  +  1*2  +  0*1  +  0*0  =  6`。不可思议，对吧？！但你得注意，唯一的例外是数字 0，按权重公式计算的话，它的结果是 11。

**任务来了：**
使用指定语言创建一个程序，它具备如下功能（如果它有一个界面就简直棒极了）：
打印菜单，让用户可以选择程序的三个功能：
* 用户可以输入一个邮编（5 位，9 位，或 10 位：9 位就是 10 位把“-”去掉后的样子），把它转换成一个「条码」（记得不要编码那个减号“-”）
* 用户可以输入一个「条码」，程序把它转回邮编，如果是 9 位的，记得加个“-”
* 退出

注意：
* 所有的输出都要打印给用户。
* 所有输入都要进行校验。
```
Validation Check:       45056-1234   ==   |:|::|:|:|:||::::|:|::||:::::||::|:|::||::|::|||:::|

cd is 0
```

请完成一个命令行程序，程序开始的时候会打印：

    1. Translate zip code to bar code
    2. Translate bar code to zip code
    3. Quit
    Please input your choices(1~3)

当你输入1，并且回车，程序会打印：

    Please input zip code:

当你输入2，并且回车，程序会打印：

    Please input bar code:
    
任何时候，你输入错误，程序会打印：

    Please give right input
  
---

* <https://en.wikipedia.org/wiki/POSTNET>
* <https://www.cs.drexel.edu/~introcs/Fa12/assignments/HW4/index.html>
* <http://www.jiskha.com/>
For faster sorting of letters, The United States Postal Service encourages companies that send large volumes of mail to use a barcode denoting the ZIP code.  This type of barcode uses single lined bars of two different heights.  In the following chart each number from 0 to 9 is denoted by it’s barcode equivalent.  The vertical lines represent the long lines while the colons represent the short lines.

    1	:::||
    2	::|:|
    3	::||:
    4	:|::|
    5	:|:|:
    6	:||::
    7	|:::|
    8	|::|:
    9	|:|::
    0	||:::

```
Example:	|	|:|::	:|:|:	|:::|	:::||	::||:	:|:|:	|
Bar Code	Frame	Digit-1	Digit-2	Digit-3	Digit-4	Digit-5	CD	Frame
95713	Bar	(9)	(5)	(7)	(1)	(3)	(5)	Bar
```
There are full-height Frame Bars on each side of the whole barcode .  Each number of the zip code is encoded with the barcode equivalent.  After each digit of the zip code has been bar coded it is followed by a “Check Digit”, which is computed as follows: Add up all digits that comprise the zip code, and calculate the number (check digit) that will make this sum a multiple of 10.  For example, the zip code 95713 has a sum of digits that equal 25; therefore, the number needed to make 25 into a multiple of 10 would be 5 – making the total of the digits equal to 30.  This is called the check digit.  Each digit of the zip code, and the check digit, is encoded according to the following table (note: this is only a numerical representation of the chart above where 1 denotes a full bar and 0 denotes a half bar):

        7	4	2	1	0
    1	0	0	0	1	1
    2	0	0	1	0	1
    3	0	0	1	1	0
    4	0	1	0	0	1
    5	0	1	0	1	0
    6	0	1	1	0	0
    7	1	0	0	0	1
    8	1	0	0	1	0
    9	1	0	1	0	0
    0	1	1	0	0	0


Note that they represent all combinations of two full and three half bars.  The digit can be easily computed from the barcode using the column weights 7, 4, 2, 1, 0.  For example, barcode digit 6 is written as: 01100 so if we want to convert from this barcode number back to what it is equal to we simply use the form: 0*7  +  1*4  +  1*2  +  0*1  +  0*0  =  6.  The only exception is 0, which would yield eleven according to the weight formula so you will need to compute for that.

Create a java program that will perform the following functions (Optionally you can create this app in a GUI):
Print a menu for the user to select one of the three options:
Allow user to enter a zip code (5, 9, or 10 characters: the 9 digit zip is a 10 digit zip without the hyphen) and convert it to a barcode (you, of course, do not encode the hyphen)
Allow user to enter the barcode and have it convert it back to a zip code.  Insert a hyphen for the 9 digit zips
Quit
(check digit)You will need to print all output for the user.
You will need to validate user entries for all data input.


Validation Check:       45056-1234   ==   |:|::|:|:|:||::::|:|::||:::::||::|:|::||::|::|||:::|

cd is 0


e.g.

finish a Cli application. start with

    1. Translate zip code to bar code
    2. Translate bar code to zip code
    3. Quit
    Please input your choices(1~3)

When you input '1' and press enter

    Please input zip code:


When you input '2' and press enter

    Please input bar code:
    
Any time when you input wrong, you would get these output:
    
    Please give right input
    
    
    
    
    
     
