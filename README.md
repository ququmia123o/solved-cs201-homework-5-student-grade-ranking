Download Link: https://assignmentchef.com/product/solved-cs201-homework-5-student-grade-ranking
<br>






<strong>Processing</strong>

You can use a struct data structure to encapsulate data of one student, such as student name, points, etc. It is up to you to decide which fields are to be included in this struct.

You can use a vector to store several students’ data. Of course, the element type of this vector will be the previously defined student struct. Here please remark that you CANNOT make any assumption about the number of students in the course. The sample grades data file that we provided in the google drive folder is partially taken from the results of a course. You can observe from this sample that there are different numbers of students in each assessment list. Therefore, your program should work for any number of students. Moreover, your program should work for any student names which are consistent with the naming rules discussed in the <em>Input File </em>Section. In the sample, we used real student names from a previous class, but we can use other names for grading purposes.

The points table is a sorted list of students rankings. The order is determined by the total points that each student gained through all course assessments in a specific course. If there is a tie in points meaning there are two students with the same points, some other criteria will be used to determine the order. These details will be explained below.

Flow of the program may be as follows:

− Your program should first ask for file name information from the user for the input files. Then, the user enters these file names from the keyboard. After that, your program opens the input files and tests for failure. <u>If it fails to open any of these files, then the program will terminate with an appropriate message (see sample runs for the message).</u>

− If it opens all of the files successfully, then your program processes the input files. The processing method will be line by line since there is data for a specific student on each line for the input files of <em>student information </em>and <em>grade results.</em>

<ul>

 <li>Regarding processing the input files, first, you need to calculate the <em>total points that a student achieved </em>at the end of the course by using ID information since there is no name information in the <em>grade results </em>file (i.e. also name information is not unique to search for a</li>

</ul>

student).

<ul>

 <li>As mentioned in the <em>Input File </em>Section, there are grades for different assessments of a course in the input file of <em>grade results</em>. A particular assessment starts with ***Homework***, ***Midterm***, or ***Final*** tag. After one of these tags, we have the student ID number and his/her grade for the corresponding assessment (one student data per line). <u>You need to differentiate these tags as you read them since each of them has a distinct weight and will contribute to the <em>total points </em>of a student at various levels</u>. The <em>total points </em>of the student will be the <em>weighted sum of the grades </em>that s/he achieved for these specific evaluations (i.e. tags).</li>

 <li>The processing for each student of the particular assessment section in the <em>grade results </em>file is as follows (note that this is just a suggested algorithm, and there could be other ways to solve this, so please feel free to create your own algorithm as well as using this one):

  <ul>

   <li>If this student is not in the vector (i.e. if this is his/her first appearance in the <em>grade results </em>file), then create a new student struct for this student and add to the vector. As you process the <em>grade results </em>file, you should retrieve the names of the corresponding student on that line from the <em>students </em>file by using the ID number (i.e. ID number exists in both of the input files).</li>

   <li>If this student is already in your vector, update this existing student struct. That is, if this student has occurred before in the <em>grade results </em>file, then there should be a struct in the vector for him/her. If this is the case, you should only update the necessary information about the corresponding student without adding a struct for him/her to the vector again.</li>

   <li><u>Updating the data of a specific student</u>: Update the total point of a student by adding the <em>weighted sum of the points </em>gained from the particular assessment to his/her previous points. The weights for each evaluation scheme of a course are given below. The number of assignments (i.e. homework) and midterms will be more than one since the sum of the weight percentages should be equal to 100% (i.e. overall course grade will be computed from all of these particular assessments). You may assume the total percentage of these in the file will sum up to 100%, however do not make any assumptions of the number of each assessment. For example; there could be 3 homework assignments, 2 midterms and 1 final as given in the grades.txt file OR 1 homework, 3 midterms and 1 final OR 5 midterms and 0 homework and final as given in the grades2.txt file in the homework drive folder.</li>

  </ul></li>

</ul>

<table width="176">

 <tbody>

  <tr>

   <td width="89"><strong>Particular Assessment</strong></td>

   <td width="87"><strong>Weight</strong><strong>Percentage</strong></td>

  </tr>

  <tr>

   <td width="89">Homework</td>

   <td width="87">10%</td>

  </tr>

  <tr>

   <td width="89">Midterm</td>

   <td width="87">20%</td>

  </tr>

  <tr>

   <td width="89">Final</td>

   <td width="87">30%</td>

  </tr>

 </tbody>

</table>

− After your program finishes reading and processing all of the information in the input file of <em>grade results </em>and storing the necessary data in the vector, it should sort the vector in descending manner.

<ul>

 <li>You may modify and use one of sorting algorithms provided by the book and/or discussed in the lecture. If you want to develop your own sorting algorithm, of course you may, but this will be more difficult.</li>

 <li>You should sort the vector by <em>points</em>; students with higher <em>points </em>must be at higher positions in the table. If multiple students have the same <em>point</em>, then you should use the <em>last name </em>of the student; in this case the student with alphabetically smaller last name (in string comparison terms) must be at a higher position in the table. <u>If multiple students have both the same <em>point </em>and <em>last name</em>, then they should be in any order in the table</u>. You do not need to worry about it.</li>

</ul>

− Finally you display the message “<em>Enter the rank you want to query (enter 0 to exit):</em>” that asks the user to enter the rank number to query for. You will display this query message until the user enters 0 to exit the program.

<strong>Output</strong>

After your program has the sorted point table and the user enters a rank integer, the student information with the given rank is displayed on the screen. Four pieces of information must be displayed for the student queried; these are <em>Rank of the student in the points table</em>, <em>ID number of the student, Name of the student (i.e. first name, middle name if exists and last name), Points that the student gained</em>. <strong>These four pieces of information must be displayed <u>in this order </u>and <u>there must be commas in between</u>.</strong>

For the name of the student <u>in the output</u>, please use the following formats for the possible two cases (NO ADDITIONAL SPACES!):

<ol>

 <li>FirstName-SingleSpace-MiddleName-SingleSpace-LastName (middle name exists) Example: Ali(space)Can(space)Akdeniz</li>

 <li>FirstName-SingleSpace-LastName (there is no middle name)</li>

</ol>

Example: <span style="text-decoration: line-through;">Gizem(space)(space)Gezici </span>(wrong),                            it   should   be

Gizem(space)Gezici (right)

In the google drive folder of this homework, we provide sample input files (students.txt, grades.txt with an example ranking table file also (results.txt). You may examine and of course use them to understand the homework and output format in detail.

Please see the sample runs for examples using these given input files.

<strong>Sample Runs</strong>

Below, we provide a sample run of the program that you will develop. The italic and bold phrases are inputs taken from the user. You should follow the input order in these examples and the prompts your program will display must be <strong>exactly the same </strong>as in the following examples.

<strong>Sample Run 1</strong>

Please enter a filename for Students Grades Results: <strong><em>grades </em></strong>Can not find the requested file. Terminating application …

<strong>Sample Run 2</strong>

Please enter a filename for Students Grades Results: <strong><em>grades.txt </em></strong>Please enter a filename for Students Names : <strong><em>nothere.txt </em></strong>Can not find the requested file. Terminating application …

<strong>Sample Run 3</strong>

Please enter a filename for Students Grades Results: grades.txt

Please enter a filename for Students Names : students.txt

<h1>Enter the rank you want to query (enter 0 to exit): 1</h1>

1, 00012287, Onur Akdeniz, 81.2

Enter the rank you want to query (enter 0 to exit): 4

<h1>4, 00011464, Alper Aydin, 74.7</h1>

Enter the rank you want to query (enter 0 to exit): 4

4, 00011464, Alper Aydin, 74.7

Enter the rank you want to query (enter 0 to exit): 19 Rank needs to be greater than 0 and smaller than 16!

Enter the rank you want to query (enter 0 to exit): 11

11, 00010926, Ekrem Sinan Aygun, 60.5

Enter the rank you want to query (enter 0 to exit): 7

7, 00011530, Burcu Aciksoz, 66.2

Enter the rank you want to query (enter 0 to exit): 8

8, 00010206, Gizem Gezici, 66.2

<h1>Enter the rank you want to query (enter 0 to exit): 14</h1>

<h1>14, 00011412, Yonca Betul Karadeniz, 57.5</h1>

Enter the rank you want to query (enter 0 to exit): 2

2, 00009029, Ali Can Akdeniz, 74.9

Enter the rank you want to query (enter 0 to exit): 15

15, 00008963, Selcuk Akaydin, 50.8

Enter the rank you want to query (enter 0 to exit): -5 Rank needs to be greater than 0 and smaller than 16! Enter the rank you want to query (enter 0 to exit): 314323 Rank needs to be greater than 0 and smaller than 16!

Enter the rank you want to query (enter 0 to exit): 5

5, 00009713, Ozge Karadeniz, 68.9

Enter the rank you want to query (enter 0 to exit): 0 Exiting…

<strong>Sample Run 4</strong>

Please enter a filename for Students Grades Results: grades2.txt

Please enter a filename for Students Names : students.txt Enter the rank you want to query (enter 0 to exit): 15 Rank needs to be greater than 0 and smaller than 14!

Enter the rank you want to query (enter 0 to exit): 13

13, 00011366, Yigit Akar, 54.6

Enter the rank you want to query (enter 0 to exit): 1

1, 00012287, Onur Akdeniz, 83

Enter the rank you want to query (enter 0 to exit): 5

5, 00009713, Ozge Karadeniz, 72.4

Enter the rank you want to query (enter 0 to exit): 0 Exiting…


