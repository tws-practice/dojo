https://en.wikipedia.org/wiki/POSTNET
https://www.cs.drexel.edu/~introcs/Fa12/assignments/HW4/index.html
http://www.jiskha.com/
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

Example:	|	|:|::	:|:|:	|:::|	:::||	::||:	:|:|:	|
Bar Code	Frame	Digit-1	Digit-2	Digit-3	Digit-4	Digit-5	CD	Frame
95713	Bar	(9)	(5)	(7)	(1)	(3)	(5)	Bar

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


Validation Check:       

45056-1234   ==   |:|::|:|:|:||::::|:|::||:::::||::|:|::||::|::|||:::|

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
    
    
    
    
    
     