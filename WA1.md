# 1.grep -A 1 dog WA1.fasta | head -2 | sed 's/dog/rabbit/' > animal2.txt

purpose : 
to output a new file named animal2.txt containing the first sequence of dog in the fasta file and correct a wrong named sequence.


(1)grep -A 1 means: display lines that contain "dog" and also the next line after "dog" (-A 1 : one line after; -A: after)

the output should be
>alpha_globin_dog P60529 Canis lupus familiaris (dog)
VLSPADKTNIKSTWDKIGGHAGDYGGEALDRTFQSFPTTKTYFPHFDLSPGSAQVKAHGKKVADALTTAVAHLDDLPGALSALSDLHAYKLRVDPVNFKLLSHCLLVTLACHHPTEFTPAVHASLDKFFAAVSTVLTSKYR
>beta_globin_dog XP_537902 Canis lupus familiaris (dog)
MVHLTAEEKSLVSGLWGKVNVDEVGGEALGRLLIVYPWTQRFFDSFGDLSTPDAVMSNAKVKAHGKKVLNSFSDGLKNLDNLKGTFAKLSELHCDKLHVDPENFKLLGNVLVCVLAHHFGKEFTPQVQAAYQKVVAGVANALAHKYH

 (2)| head -2 : after searching lines only have dogs and their next lines, use head -2 to filter all but first two of lines (in the fasta file.
 
 the output should be 
 >alpha_globin_dog P60529 Canis lupus familiaris (dog)
VLSPADKTNIKSTWDKIGGHAGDYGGEALDRTFQSFPTTKTYFPHFDLSPGSAQVKAHGKKVADALTTAVAHLDDLPGALSALSDLHAYKLRVDPVNFKLLSHCLLVTLACHHPTEFTPAVHASLDKFFAAVSTVLTSKYR 

 (3)| sed 's/dog/rabbit/' : is to change the word of "dog" to "rabbit" 
 
  the output should be 
  >alpha_globin_rabbit P60529 Canis lupus familiaris (rabbit)
VLSPADKTNIKSTWDKIGGHAGDYGGEALDRTFQSFPTTKTYFPHFDLSPGSAQVKAHGKKVADALTTAVAHLDDLPGALSALSDLHAYKLRVDPVNFKLLSHCLLVTLACHHPTEFTPAVHASLDKFFAAVSTVLTSKYR

 (4)> animal2.txt : output the changed file to animal2.txt, so in animal2.txt we have 
 
   >alpha_globin_rabbit P60529 Canis lupus familiaris (rabbit)
VLSPADKTNIKSTWDKIGGHAGDYGGEALDRTFQSFPTTKTYFPHFDLSPGSAQVKAHGKKVADALTTAVAHLDDLPGALSALSDLHAYKLRVDPVNFKLLSHCLLVTLACHHPTEFTPAVHASLDKFFAAVSTVLTSKYR
 
# Problem:
 I want to put those sequences in alphabetical order and remain its name above as well, however, I don't know how to use sort to sort two lines together [since fasta file has two lines for each sequence and using sort only gets a mess])
 
 
 
# 2. grep kangaroo WA1.fasta | sort

purpose : only want to see what sequences are from kangaroos and sort them in alphabetical order to help us extract information quickly

grep kangaroo WA1.fasta : this will find the lines contain the word of "kangaroo"

the output should be
>myoglobin_kangaroo P02194 Macropus rufus (red kangaroo)
>alpha_globin_kangaroo P01975 Macropus giganteus (eastern gray kangaroo)
>beta_globin_kangaroo P02106 Macropus giganteus (eastern gray kangaroo)


| sort : put protein names in alphabetical order

the output should be 
>alpha_globin_kangaroo P01975 Macropus giganteus (eastern gray kangaroo)
>beta_globin_kangaroo P02106 Macropus giganteus (eastern gray kangaroo)
>myoglobin_kangaroo P02194 Macropus rufus (red kangaroo)

# 3. grep dog WA1.fasta | wc

grep dog WA1.fasta : want to see how many sequences are from dogs

the output should be 
>alpha_globin_dog P60529 Canis lupus familiaris (dog)
>beta_globin_dog XP_537902 Canis lupus familiaris (dog)

wc : wc will count the number of lines, the number of words and the number of bytes for these two lines we have

the output should be 
2  14  n(n for bytes)
