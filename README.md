awk-1liners
===========
##### replace all spaces w/ a single tab. due to cut not working for PLINK.genome format
##### change spaces to tabs
##### read from a text file pass to variable and do something
##### reattach a screen after forced logout
##### deletes empty files in a directory
##### substitute pattern 1st by pattern 2nd in Field6, print all to file
##### calculates the average of column 5
##### counts the number of occurrences in column 5 greater than .2 and less than .8, prints count
##### remove last line
##### remove first line
##### turn 5 spaces into a tab (unexpand/expand)
##### awk command that cut down alignment to 70bp
##### takes first 1000 reads of bam file converts to sam file and stores in test.bam
##### gets insert size from bam
##### returns only unique alignments from samtools
##### returns max and min from a column
##### removes PairedContig_ or something and replaces w/ blank or something
##### paste by columns
##### replaces things in FILE1 with thing in FILE2 by matching; in this case I added contig lengths to freebayes vcf.
	#1. first buffer the file2 data in the form of key, value pair (associative array). and I have used key as col1 and value as entire line.
	#2. then check whether array key is exist for column 1 in file1 (joining columns) if yes, then replace file1 current value (i.e $0) with current value in array, if not skip it.
	#3. finally print the data.
	#e.g. awk -F, 'NR==FNR{a[$1]=$0;next;}a[$1]{$0=a[$1]}1' contig_lengths.txt WbPNGL3_POP-filt.snps.freebayes.out.vcf > WbPNGL3_POP_LEN-filt.snps.freebayes.out.vcf
##### replaces non-ACGT codes with "N" in the REF column; T/T=T T/C=Y
##### Calculates the difference between 2 columns, here used to get the length of LowComplexityRegions output by mdust
##### checks that the reference allele field is not a complex variant as output by freebayes, as this causes errors w/ vcftools
##### replaces ambiguous bases in reference w/ N (credit to Brad Chapman as fix_ambig)
