## THe following commands gave me the 100000 random snps for the subsetting

sed '1d' out.GT.FORMAT_2  > tmpfile; mv tmpfile out.GT.FORMAT_2 
shuf <out.GT.FORMAT_2> tmp
head -n 100000 tmp > out1
sort -k1,1 -k2,2n  out1 > Random_100000_SNP
cat header.txt Random_100000_SNP > tmpfile; mv tmpfile Random_100000_SNP
