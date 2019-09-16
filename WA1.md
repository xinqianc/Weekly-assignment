grep -A 1 dog WA1.fasta | head -2 | sed 's/dog/rabbit/' > animal2.txt

# purpose : 
to output a new file named animal2.txt containing the first sequence of dog in the fasta file and correct a wrong named sequence.


#
(1)grep -A 1 means: display lines that contain "dog" and also the next line after "dog" (-A 1 : one line after; -A: after)
 (2)| head -2 : after searching lines only have dogs and their next lines, use head -2 to filter all but two of lines (in the fasta file. it should be > alpha ......(dog) line and VLSPADK..line )
 (3)| sed 's/dog/rabbit/' : is to change the word of "dog" to "rabbit" (to correct the mistake)
 (4)> animal2.txt : output the changed file to animal2.txt, so in animal2.txt we have > alpha ......(rabbit) line and VLSPADK..line
 
 Problem:
 I don't know how to use sort in this fasta file (I want to put those sequences in alphabetical order and remain its name above, however, I don't know how to use sort to sort two lines together [since fasta file has two lines for each sequence])
 
