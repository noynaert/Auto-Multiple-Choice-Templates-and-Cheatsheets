# Auto-multiple-choice Templates and Cheatsheet

These notes are for the auto-multiple-choice test generator for Linux.  [https://www.auto-multiple-choice.net/index.en])https://www.auto-multiple-choice.net/index.en) Specifically it is for the text version of the system.

I love the auto-multiple-choice package.  I hate the documentation.  The documentation for the text package reads like the author was trying to say the absolute bare minimum necessary.  Many questions are left unanswered, and the limited number of examples are sometimes not very helpful.   

## Disclaimer

I am not associated with the project.  I don't even understand a lot of it.  This document is simply a list of some code snippets that I have gotten to work for me.

Also, I am not an authority in LaTeX.  I should have learned LaTeX years ago, but didn't.  The LaTeX I have in this document is just stuff I have cobbled together for exams.  Please don't ask me LaTeX questions, especially if you want a correct answer!

## Sample Exam Header

This is a sample header I put on exams.  It allows LaTeX.  Also, it inserts a bulleted list into the header of the document using raw LaTeX.

The bulleted list may be lifted from the header and inserted into questions if they need a bullet list.


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


## Using the templates

### Using Essay Templates

For essay questions add your text after the *<line=n>* text. An example is below.

I do have a peculiarity in my exams because I take off 1 point if a student leaves the question blank.  I do that to discourage students from skipping essay questions.  You may delte the -1 No Answer if you want to get rid of this option.      

```text
*<lines=3> Explain the universe and give two examples (3 points).
-[0]{-1} [*-1 No Answer*]
-[O]{0} 0
-[P]{1} 1
-[P]{2} 2
+[V]{3} [_3 Correct_]
```

### Using Multiple Choice Templates

For multiple choice add your text after the curly braces.  Then add the foils
after the + or - signs Make sure there is only one correct answer.  I generally
put the correct answer first and let amc shuffle the foils.

```*[next]{b=2,m=0} What color was George Washington's white horse?
+ white
- black
- tan
- red
```

## Essay (templates for 2 to 5 points)

```text
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
```

# MC Multiple Choice

```text
*[next]{b=2,m=0} 
+ 
- 
- 
- 
```

## True False (As True)

```text
*[ordered]{b=2,m=0} 
+ TRUE 
- FALSE 
```

## True False (As False)

```text
*[ordered]{b=2,m=0} 
- TRUE 
+ FALSE 
```


## Example of puting a picture in a question

**[ordered]{b=2,m=0} The following image contains different attempts to
abstract classes.  Mark all of the answers that are correct (there may be more than one correct answer.) 
\\
![height=6cm]images/abstract.png!
- Option a
- Option b
+ Option c
+ Option d

## Example of using verbatim to control formatting

*[ordered]{b=2,m=0} Does the return statement in the following method cause a syntax error?
[verbatim]
    public static int yMethod(double a, double b){
        System.out.println(a+b);
        return a + b;
    }
[/verbatim]
- YES, It causes a syntax error.
+ NO, It does not cause a Syntax error.

## Including a picture and a caption

\begin{figure}
  \caption{A picture of a star.}
  \centering
    \includegraphics[width=2cm]{./images/star.png}
\end{figure}

```