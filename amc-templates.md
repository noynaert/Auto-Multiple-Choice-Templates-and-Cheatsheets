#Auto-multiple-choice Templates and Cheatsheet

These notes are for the auto-multiple-choice test generator for Linux.  [https://www.auto-multiple-choice.net/index.en])https://www.auto-multiple-choice.net/index.en) Specifically it is for the text version of the system.

I love the auto-multiple-choice package.  I hate the documentation.  The documentation for the text package reads like the author was trying to say the absolute bare minimum necessary.  Many questions are left unanswered, and the limited number of examples are sometimes not very helpful.   

## Disclaimer

I am not associated with the project.  I don't even understand a lot of it.  This document is simply a list of some code snippets that I have gotten to work for me.

Also, I am not an authority in LaTeX.  I should have learned LaTeX years ago, but didn't.  The LaTeX I have in this document is just stuff I have cobbled together for exams.  Please don't ask me LaTeX questions, especially if you want a correct answer!

## Sample Exam Header

This is a sample header I put on exams.  It allows LaTeX.  Also, it inserts a bulleted list into the header of the document using raw LaTeX.

The bulleted list may be lifted from the header and inserted into questions if they need a bullet list.

```text
# AMC-TXT source file
Title: Exam 01, CSC 254, Fall 2018
PaperSize: letter
ShuffleQuestions:0
LaTeX: 1
Presentation: 
\begin{itemize}
   \item Select the best answer for each question
   \item This exam is closed book
   \item Answers are worth 2 points unless otherwise noted.
   \item Use an X to mark your answers.  
   \item I will have whiteout available if you make a mistake.
   \item Questions relate to Java 10 and 11. 
   \item Use proper Java style and capitalization in your answers.
\end{itemize}


*<lines=3> Describe the relationship between an object and its defining class.
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
-[P]{2} 2
+[V]{3} [_3 Correct_]

*[next]{b=2,m=0} Which of the following keywords is used to define a class?
+ class
- new
- interface
- public
 
*[ordered]{b=2,m=0} An array may contain elements of an object type.
+ TRUE 
- FALSE 
**[ordered]{b=2,m=0} The following image contains different attempts to
abstract classes.  Mark all of the answers that are correct (there may be more than one correct answer.) 
\\
![height=6cm]images/abstract.png!
- Option a
- Option b
+ Option c
+ Option d


*<lines=3> (2 points)
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
+[V]{2} [_2 Correct_]

*<lines=4> (3 points)
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
-[P]{2} 2
+[V]{3} [_3 Correct_]

*<lines=4> (4 points)
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
-[P]{2} 2
-[P]{3} 3
+[V]{4} [_4 Correct_]

*<lines=7> (5 points)
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
-[P]{2} 2
-[P]{3} 3
-[V]{4} 4
+[V]{5} [_5 Correct_]

*[ordered]{b=2,m=0} Does the return statement in the following method cause a syntax error?
[verbatim]
    public static int yMethod(double a, double b){
        System.out.println(a+b);
        return a + b;
    }
[/verbatim]
- YES, It causes a syntax error.
+ NO, It does not cause a Syntax error.


*<lines=3> [== The rest of this exam is like Exam 2 ==]  For the rest of these
questions, you will be writing about a class called "Circle."  The circle class has one
data member.  It is a double named "radius."\\
In the space below write the constructor for this class.  The constructor
takes ones argument which is the radius.  You may either set the value of the radius
directly, or you may assume that there is a suitable setter.
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
-[P]{2} 2
+[V]{3} [_3 Correct_]


\begin{figure}
  \caption{A picture of a star.}
  \centering
    \includegraphics[width=2cm]{./images/star.png}
\end{figure}

```