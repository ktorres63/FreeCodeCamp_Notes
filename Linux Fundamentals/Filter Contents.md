## less 
We will notice on the man page that it contains many more features than **more** 
## Sort
Depending on which results and files are dealt with , they are rarely sorted. Often it's neccesary to sort the desired results alphabeticaly or numering to get a better overview. For this we will use a tool called sort
![[sort.png]]
![[sort2.png]]
## Grep
![[grep.png]]
We use  -v to exclude specific results. In the example we exclude all users who have disabled the standard shell with the name "/bin/false" or "/usr/bin/nologin"
![[grep2.png]]

## Cut
Specific results with different chracters may be separate as delimiters. Here it is handy to know how to remove specific delimiters and show the words on a line in a specified position. One of the tools that can be used for this is cut. We use -d option and set the delimiter to the colon chracter(:) and define with the option "-f" the position in the line we want to output

Is like to generate a table with -d generate a column and with -f we choose the column, in this example we shows the column 1 (f1)
![[cut.png]]

## Tr
To replace certain characters from a line with characters we use the tool tr, as the first option we define which character we want to replace, and as a second option, we define the chracter we want to replace it with
![[tr.png]]

## Column 
The tool column is well suited to display such results in tabular form using the "-t"
![[column1.png]]
![[column2.png]]

## Awk

The (g)awk programming is beneficial, which allows us to siplay the first ($1) and last (\$NF) result of the line
![[awk.png]]

## Sed

if we want to change specific name in the whole file or standard input, we can use sed. Sed is one of the most common uses of this is substituting text. sed looks for patterns we have efine in the form of regular expressions and replaces them with another pattern that we have also defined. 
The s flag stands for the beginning command, We specified the pattern to replace and finally we use the g flag which stands for replacing all matches
![[sed.png]]

## Wc 
To avoid counting the lines or chracters manually, we can use the tool wc wc, with the flag -l 
![[wc.png]]