Download Link: https://assignmentchef.com/product/solved-csci1913-lab-4
<br>
This laboratory assignment is intended as a short introduction to Java for students who are already familiar with C or C++. It asks you to rewrite the Python class Zillion from Lab 2 in Java. Like the Python class, the Java class Zillion implements a decimal counter.

However, since you will be using a Java array instead of a Python list, your counter will have a fixed maximum number of digits.

<ol>

 <li></li>

</ol>

All the code in this example goes inside the main method of your driver class. It first creates an instance of Zillion in the variable counter, like this.

Zillion counter = new Zillion(12);

The instance of Zillion can hold up to twelve decimal digits. Its initial value is 000000000000. Note that twelve digits can represent a much larger number than will fit in a 32-bit Java int, which is only 2 147 483 647, or around two billion. The main method then adds 1 to the counter by calling the method increment, like this.

counter.increment();

Now the counter contains 000000000001. The main method now prints the counter like this. Java automatically calls counter’s toString method when you try to print it.

System.out.println(counter);

You should see 000000000001 printed. If you call increment again, and then print the counter, then you should see 000000000002. If you call increment and print the counter one more time, then you should see 000000000003, etc.

<ol start="2">

 <li></li>

</ol>

Your class Zillion must represent the digits of a number using a private array of integers (int’s). Each digit <em>d</em> in the array must be an integer 0 ≤ <em>d</em> ≤ 9. For example, suppose that your array is called digits, has a length of 3, and represents the number 57. Then digits[0] is 0, digits[1] is 5, and digits[2] is 7.

The method increment must work like this. Starting at the right end of the array, and moving toward the left end, it must change 9’s into 0’s, until it finds a digit that is not 9, or until there are no more digits left to be visited. If it stops because it has visited a digit that is not 9, then it must add 1 to that digit. If it stops because there are no more digits left, then the counter has overflowed and it must not do anything else. For example, if your counter has three digits, and represents the integer 999, then incrementing it must produce 000. It must not indicate an error in any way.

<ol start="3">

 <li></li>

</ol>

The class Zillion must have all the following methods. To simplify grading, your methods must use the same names as these. However, they need not use the same parameter names.

public Zillion(int size)

Constructor. Create a private array of size integers (int’s). You may assume that size is greater than or equal to 0. You need not initialize the array, because Java initializes all the elements to 0 for you.

public void increment()

Increment the counter, using the algorithm described in part <strong>2.</strong> One way to do that is by using a while loop; there may be other ways. If the counter contains all 9’s, then you must not generate an illegal array index.

public String toString()

Convert the digits in the counter to a String, and return that String. One way to do that is by using a for loop that concatenates all the digits of the array together using the operator +. Java automatically converts an integer to a string when you concatenate it to a string.

<ol start="4">

 <li><strong> Tests.</strong></li>

</ol>

The file <a href="https://html2pdf.com/files/xx1q95q6ou8qd827/o_1e0djmtd4n7uq3kkb8vmu13d0b/Driver.java"><strong>Driver.java</strong></a> contains Java source code for a driver class, unimaginatively called Driver. This class contains a main method, which in turn contains code that tests your class Zillion. The class Zillion must <em>not</em> contain the main method! To grade your work, the TA’s will run the main method in Driver. If a test succeeds, then you will receive all the points for that test. If a test fails, then you will receive no points for that test.