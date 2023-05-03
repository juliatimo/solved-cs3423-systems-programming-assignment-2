Download Link: https://assignmentchef.com/product/solved-cs3423-systems-programming-assignment-2
<br>
sed




For this assignment, you will use <strong>sed </strong>and <strong>bash </strong>to create a program for formatting C code. Your program should take a source code file as input and apply the following:

<ul>

 <li>No more than one space between tokens.</li>

 <li>No trailing whitespace after a line.</li>

 <li>Binary operators should always surrounded by a single space on either side (including assignment and Boolean operators). Only the following operators must be accounted for: <strong><sub>+</sub></strong>, <strong><sub>–</sub></strong>, <strong><sub>*</sub></strong>, <strong><sub>/</sub></strong>,</li>

</ul>

<strong>!=</strong>, <strong>=</strong>, <strong>==</strong>, <strong>&lt;=</strong>, <strong>&gt;=</strong>, <strong>&lt;</strong>, <strong>&gt;</strong>, <strong>&amp;&amp;</strong>, <strong>||</strong>, and <strong>ˆ</strong>.

<ul>

 <li>Conditions should not have whitespace immediately inside of either the opening or closing parentheses. Further, a parenthetical condition should not possess any whitespace preceding it.</li>

 <li>The program should <em>not </em>modify spaces which are leading, expanded tabs.</li>

 <li>The program should ensure that each opening curly brace, that does not begin the line it is on (excluding existing whitespace), should have at least one space character preceding it.</li>

 <li>The contents of comments should be left alone. You may behave as though comments (either single- or multi-line) will not appear on lines with source code.</li>

</ul>

<strong><u>Note: </u></strong>Do to the use of the “&lt;” and “&gt;” “operators” in preprocessor directives, ignore all lines consisting of preprocessor directives (e.g., lines beginning with zero or more whitespace, followed by a hash (“#”) character).

<strong><u>Note: </u></strong>Do not be concerned with changes in strings; if any such replacement changes the contents of a string, this need not be corrected for, nor will it be considered an issue.

<strong><u>Hint: </u></strong>All of the above does not need to be done in a single pass.

This assignment requires only sed and bash. <strong>Do not </strong>use awk, Python, or any other languages/utilities.

<h1>Example</h1>

In the code below, underscores (_) represent spaces in the source code. Note that there are no changes to comments or pre-processor directives (i.e. #include) lines.

<strong>Input (inputProgram.c):</strong>

<h2>1 /** 2 author:_____some_student 3 **/</h2>

4 #include_&lt;stdio.h&gt;

5

<ul>

 <li>int_main()_{</li>

 <li>____int_numberIn;</li>

</ul>

8

9 ____printf(“Enter_a_number:_”);

10

11 ____scanf(“%d”,_&amp;numberIn);__

12

13 ____if_(_numberIn_&gt;_10_)_{

<h2>14 ____//____add__two</h2>

15 ________return_numberIn_+__2; 16 ____}_else___if____(numberIn&lt;___5){

<h2>17 ____//____subtract_two___</h2>

18 ________return__numberIn_-_2;

19

20 ____int____isNumOdd__=_numberIn__%__2;

21

<ul>

 <li>____return__numberIn*2;</li>

 <li><sub>}</sub></li>

</ul>

<strong>Output (outputProgram.c):</strong>

<h2>1 /** 2 author:_____some_student 3 **/</h2>

4 #include_&lt;stdio.h&gt;

5

<ul>

 <li>int_main()_{</li>

 <li>____int_numberIn;</li>

</ul>

8

9 ____printf(“Enter_a_number:_”);

10

11 ____scanf(“%d”,_&amp;numberIn);

12

13 ____if(numberIn_&gt;_10)_{

<h2>14 ____//____add__two</h2>

15 ________return_numberIn_+_2; 16 ____}_else_if(numberIn_&lt;_5)_{

<h2>17 ____//____subtract_two___</h2>

18 ________return_numberIn_-_2;

19

20 ____int_isNumOdd_=_numberIn_%_2;

21

<ul>

 <li>____return_numberIn_*_2;</li>

 <li><sub>}</sub></li>

</ul>

<h1>Script Execution</h1>

Your program should be invoked through a single bash file (see below) with the path to the input program as the argument. The resulting output file should be printed directly to stdout.

<strong>$ assign2.bash /path/to/input.txt</strong>

<h1>Assignment Data</h1>

A sample input file can be found in:

<strong>/usr/local/courses/ssilvestro/cs3423/Spring20/assign2</strong>.

<h1>Script Files</h1>

Your program should consist of <em>at least </em>two files:

<ul>

 <li><strong><sub>bash </sub></strong>– the main file which is initially invoked</li>

 <li><em>At least </em>one <strong><sub>.sed </sub></strong>file which is used for a sed invocation run in <strong><sub>bash</sub></strong>. Each sed invocation should have its own <strong><sub>.sed </sub></strong>file which may contain multiple sed commands. For example, your submission may include <strong>assign2.bash</strong>, <strong>command1.sed</strong>, <strong>command2.sed</strong>, …, <strong>command</strong><em>N</em><strong><sub>.sed </sub></strong>where each <strong><sub>.sed </sub></strong>file correspond to sed invocations within <strong><sub>assign2.bash</sub></strong>.</li>

</ul>

<h1>Verifying Your Program</h1>

<strong>Your program must work for <em>any arbitrary input files </em>by applying the rules above. </strong>You can test your program with the input provided in <strong><sub>inputProgram.c </sub></strong>and compare the output with <strong>outputProgram.c </strong>using <strong><sub>diff </sub></strong>(check the man-pages on how to use the <strong><sub>diff </sub></strong>command to your requirements).


