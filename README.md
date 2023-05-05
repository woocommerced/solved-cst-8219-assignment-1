Download Link: https://assignmentchef.com/product/solved-cst-8219-assignment-1
<br>
Vector Graphic with Classes

<strong>Purpose: </strong>This assignment is a direct continuation of assignment 0 that uses C++ syntax. It uses the Stash2.h and Stash2.cpp code from the Stash2 example from “Thinking in C++” V1 (the C++ course book), so that must be added to your Visual Studio project.

Part of the code is shown on the next page; it is also on the Web Site in text files that you can copy and paste from so you don’t make any mistakes. You must use this code without modification because I will use it to mark your assignment. Your task is to implement the member functions that are declared in the GraphicElement.h and VectorGraphic.h header files and not add any new ones – your code is in the files GraphicElement.cpp and VectorGraphic.cpp.




In this assignment, when the application is running the user can

<ul>

 <li>Add a new Graphic Element (together with its lines) to the Vector Graphic</li>

 <li>Print all the details of the Graphic Elements in the Vector Graphic</li>

</ul>

<strong>An example of the output of the running application is given at the end. Yours must work identically and produce identical output. </strong>




Note the following:

<ul>

 <li>The files you submit must be named GraphicElement.cpp and VectorGraphic.cpp.</li>

 <li>you must use C++ syntax including new and delete and cin and cout</li>

 <li>You can only use functions like strlen() and strcpy() or similar etc. from the standard C library to handle strings (you cannot use the C++ string class).</li>

 <li>When the application terminates it releases <strong><u>all</u></strong> dynamically allocated memory so it does not have a resource leak (or you lose 30%).</li>

</ul>




See the Marking Sheet for how you can lose marks, but you will lose at least 60% if: you change the supplied code, it fails to build in Visual Studio 2013, it crashes in normal operation (such as printing from an empty list etc.), it doesn’t produce the example output.




Part of the code is shown on the next page. You MUST use this code <strong>without modification.</strong> Your task is to add the implementation of the functions that are declared using the style of the posted Submission Standard. All the code is in the files GraphicElement.cpp and VectorGraphic.cpp.

<strong><u>What to Submit :</u></strong> Use Blackboard to submit this assignment as a zip file (<strong>not </strong>RAR) containing only the source code files (GraphicElement.cpp and VectorGraphic.cpp). The name of the zipped folder <strong><u>must</u> </strong>contain your name as a prefix so that I can identify it, for example using my name the file would be tyleraAss1CST8219.zip. It is also vital that you include the Cover Information (as specified in the Submission Standard) as a file header in your source file so the file can be identified as yours. Use comment lines in the file to include the header.

Before you submit the code,

<ul>

 <li>check that it builds and executes in Visual Studio 2013 as you expect – if it doesn’t build for me, for whatever reason, you get a deduction of at least 60%.</li>

 <li>make sure you have submitted the correct file – if I cannot build it because the file is wrong or missing from the zip, even if it’s an honest mistake, you get 0.</li>

 <li>there’s a late penalty of 25% per day. Don’t send me file(s) as an email attachment – it will get 0.</li>

</ul>

<strong><em>             </em></strong>

<strong><em>Example code – I will use it to mark your assignment. Don’t change or add to it. </em></strong>




<table width="638">

 <tbody>

  <tr>

   <td width="55"> {public:        };#endif</td>

   <td width="264">#ifndef GRAPHICELEMENT #define GRAPHICELEMENTclass GraphicElementchar* name;Stash Lines;        // a Stash of Line objectsGraphicElement():name(nullptr),Lines(sizeof(Line)){}~GraphicElement(){if (name)                      delete []name;}char*&amp; GetName(); // Accessor Stash&amp; GetLines(); // Accessor</td>

   <td width="319">// Line.h #ifndef LINE#define LINEstruct Point{int x, y;};struct Line{Point start;Point end;}; #endif</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<table width="638">

 <tbody>

  <tr>

   <td width="319">// ass1 W17 #define _CRT_SECURE_NO_WARNINGS#define _CRTDBG_MAP_ALLOC     // need this to get the line identification//_CrtSetDbgFlag(_CRTDBG_ALLOC_MEM_DF|_CRTDBG_LEAK_CHECK_DF);// in main, after local declarations//NB must be in debug build#include &lt;crtdbg.h&gt;#include “Stash2.h”#include “Line.h”#include “GraphicElement.h”#include “VectorGraphic.h” #include &lt;iostream&gt; using namespace std; enum{ RUNNING = 1 }; VectorGraphic Image;int main(){char response;_CrtSetDbgFlag(_CRTDBG_ALLOC_MEM_DF | _CRTDBG_LEAK_CHECK_DF); while (RUNNING){     cout&lt;&lt;endl&lt;&lt;“Please select an option:
”&lt;&lt;endl;     cout&lt;&lt;“1. Add a Graphic Element
”;     cout&lt;&lt;“2. List the Graphic Elements
”;     cout&lt;&lt;“q. Quit
”;     cout&lt;&lt;“CHOICE: “;     cin&gt;&gt;response;switch (response){case ‘1’:Image.AddGraphicElement(); break;       case ‘2’:Image.ReportVectorGraphic(); break;       case ‘q’:return 0;       default:cout&lt;&lt;“Please enter a valid option
”;}cout&lt;&lt;endl;}return 0;}  </td>

   <td width="319">// VectorGraphic.h #ifndef VECTORGRAPHIC#define VECTORGRAPHIC class VectorGraphic{static const int MAX_ELEMENTS = 1024;GraphicElement Elements[MAX_ELEMENTS]; // pool of elementsunsigned int numElements;// number filled public:VectorGraphic::VectorGraphic():numElements(0){}void AddGraphicElement();            void ReportVectorGraphic();}; #endif</td>

  </tr>

 </tbody>

</table>

Example Output:







Please select an option:




<h1>1. Add a Graphic Element</h1>

<ol start="2">

 <li>List the Graphic Elements</li>

 <li>Quit</li>

</ol>

CHOICE: 1

Adding A Graphic Element

Please enter the name of the new GraphicElement(&lt;256 characters): small mouth

How many lines are there in the new GraphicElement? 1

Please enter the x coord of the start point of line index 0 -2

Please enter the y coord of the start point of line index 0 -2

Please enter the x coord of the end point of line index 0 2

<h1>Please enter the y coord of the end point of line index 0 -2</h1>







Please select an option:

<ol>

 <li>Add a Graphic Element 2. List the Graphic Elements</li>

 <li>Quit</li>

</ol>

CHOICE: 1

Adding A Graphic Element

Please enter the name of the new GraphicElement(&lt;256 characters): big nose

How many lines are there in the new GraphicElement? 4

<h1>Please enter the x coord of the start point of line index 0 -1</h1>

<h1>Please enter the y coord of the start point of line index 0 1</h1>

<h1>Please enter the x coord of the end point of line index 0 -1</h1>

Please enter the y coord of the end point of line index 0 2

Please enter the x coord of the start point of line index 1 -1

Please enter the y coord of the start point of line index 1 2

Please enter the x coord of the end point of line index 1 1

Please enter the y coord of the end point of line index 1 2

Please enter the x coord of the start point of line index 2 1

Please enter the y coord of the start point of line index 2 2

Please enter the x coord of the end point of line index 2 1

<h1>Please enter the y coord of the end point of line index 2 1</h1>

<h1>Please enter the x coord of the start point of line index 3 1</h1>

Please enter the y coord of the start point of line index 3 1

Please enter the x coord of the end point of line index 3 -1

Please enter the y coord of the end point of line index 3 1







Please select an option:




<ol>

 <li>Add a Graphic Element 2. List the Graphic Elements</li>

 <li>Quit</li>

</ol>

CHOICE: 2

VectorGraphic Report




Reporting Graphic Element #0

Graphic Element name: small mouth

Line #0 start x: -2

Line #0 start y: -2

Line #0 end x: 2

Line #0 end y: -2




Reporting Graphic Element #1

Graphic Element name: big nose

Line #0 start x: -1

Line #0 start y: 1

Line #0 end x: -1

Line #0 end y: 2

Line #1 start x: -1

Line #1 start y: 2

Line #1 end x: 1

Line #1 end y: 2

Line #2 start x: 1

Line #2 start y: 2

Line #2 end x: 1

Line #2 end y: 1

Line #3 start x: 1

Line #3 start y: 1

Line #3 end x: -1

Line #3 end y: 1







Please select an option:

<ol>

 <li>Add a Graphic Element 2. List the Graphic Elements</li>

 <li>Quit CHOICE:</li>

</ol>