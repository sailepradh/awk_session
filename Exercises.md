#### Exercise 1

##### Exercise 1.1 sum of the values
```awk
awk '{sum = sum+$1} END {print sum"\n"}' num.dat 
```

##### Exercise 1.2  the average i.e arithmetic mean value (can you write the script so it is independent from the number of rows)
```awk
awk '{sum = sum+$1} END {print sum/NR"\n"}' num.dat 
```

##### Exercise 1.3 find the maximum value
```awk
awk 'BEGIN {max = 0} {if ($1 > max) max =$1} END {print max}' num.dat
```

##### Exercise 1.4 calculate the difference between numbers in the first column, i.e 2nd-1st, 3rd-2nd etc
```awk
awk '{print $1-prev;prev=$1}' num.dat 
```

##### Exercise 01 Simple arthemetics
```awk
## cheap solution
awk '{print $1+$NF,$0}' task2.dat
```

```awk
## 3.1 Write a one-line awk script to calculate the occupied space in this folder. (*)
ls -l | awk '{sum =sum+$5} END{print sum }'
```

```awk
## 3.2 Modify the script to count only the files in your home directory (hopefully you have some in your home folder)(hint: directories begin with ”d” in the access field) (*)

ls -l | awk '{ if ($1 !~ /^d/) sum =sum+1} END { print sum}'
```

```awk
## Write a one-line awk script to add 1 to each number in the second column. (*)
awk_seminar$] awk '{print $1,$2+1,$3}' coord.dat 

## Modify the script to multiply all numbers by factor of 1.8897 . 
awk '{print 1.8897*$1,1.8997*$2,1.8897*$3}' coord.dat 
 
awk 'BEGIN {fac = 1.189} {print fac*$1,fac*$2,1.fac*$3}' coord.dat 
```


##### Exercise 02 Data extraction
 ``` awk
## Write an Awk script to collect the "MD temperature" in one column vs the "Md step" i.e.
$ awk '/MD step/{step= $3} /MD Temperature:/ {print step, $5 }' md. out

## Can you tabulate all values against the "MD step"
awk '/MD step/{step= $3; getline; press= $4; getline; pe= $5; getline; ke= $6; getline; te= $6; getline; t=$5; print step,press,pe,ke,te,t} ' Md.out 
awk 'BEGIN {RS=" K\n"} {print $3, $7, $13, $20, $27, $33}' md.out

```
##### Exercise 03 Data extraction

```awk
## You have 2 files containing results from two similar experiments.You want to calculate the difference between the numbers in the second columns. 
join -j 1 1.dat 2.dat | awk '{print $1,$2,$3,$3-$2}'

## Other possible solutions
paste 1.dat 2.dat | awk '{print $1,$2,$4,$2-$4}'

awk 'ARGIND==1 {x1=$1;y1=$2; getline < ARGV[2]; printf("%g  %g  %g  %g  %g\n",x1,y1,$1,$2,y1-$2);}' 1.dat 2.dat

awk 'BEGIN{ while (getline < ARGV[1]) {x1=$1;y1=$2; getline < ARGV[2]; printf("%g  %g  %g  %g  %g\n",x1,y1,$1,$2,y1-$2);}}' 1.dat 2.dat

## Dissecting the code : getline command does is simple thing as it causes you to be forced in the same line. ARGV[1] amd ARG[2] gives index of argument array.
```
##### Exercise 04 Easy tricks
```awk
## a) print numbers from 1 to 7 i.e. produce such output
awk 'BEGIN{ for(i=1 ;i<=7;i=i+1) print i }'

## b) print the same numbers on a single line i.e.
awk 'BEGIN{ for(i=1 ;i<=7;i=i+1) printf i" "}'

## c) print the numbers from 1 to 7 in reverse order
awk 'BEGIN{ for(i=7 ;i>=1;i=i-1) print i}'

## d) print every other number from 1 to 7 i.e. 
awk 'BEGIN{ for(i=1 ;i<=7;i=i+2) print i}'

## e) print the numbers from 1 to 2 with increments of 0.1 ie
 awk 'BEGIN{ for(i=1 ;i<=2.1;i=i+0.1) print i}'
```
