1.  copy first 5 pages of every PDF to a file.
2.  then remove ......
3.  Then displace Ia from its place. include lower case at the beginnning of the line.
4.  find the numebr of N.
5.  if the horoscope article is present in frist 5 pages then next 2 pages are copied.
6.  Problem: there are too less occurences of N. Hence words starting this character from U Dienshonhi Dictionary were borrowed and then words( ) were inserted to training file.
7.  I inserted 127 N words.
8.  insert TAB space in 52nd line throughout files for EOL

9.  remove all the empty lines from the corpus file containing 20,000 lines.
    Command: sed '/^$/d' kha01-copy.training_text > output.txt

10. insert 2 blank lines for every 52 lines.
    Command:
    #awk '1;!(NR%51){print "\t";}' output1.txt > kha.train.training_text
    #awk '1;!(NR%51){print "\t";}' output-eval.txt > kha.eval.training_text

training text = 16,318 lines, eval_text = 3,736 lines

I at the begining of lines caused hallucination effect. Hence words starting with I were placed randomly in a sentence.
The capital letter on n- N occurs very less ~1%. The occurence of this capital letter was increased to 8% by inserting words starting with N randomly in the training text file.
