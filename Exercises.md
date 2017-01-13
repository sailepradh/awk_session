#### Exercise 1

##### Exercise 1.1 sum of the values
```
awk '{sum = sum+$1} END {print sum"\n"}' num.dat 
```

##### Exercise 1.2  the average i.e arithmetic mean value (can you write the script so it is independent from the number of rows)
```
awk '{sum = sum+$1} END {print sum/NR"\n"}' num.dat 
```

##### Exercise 1.3 find the maximum value
```
awk 'BEGIN {max = 0} {if ($1 > max) max =$1} END {print max}' num.dat
```

##### Exercise 1.4 calculate the difference between numbers in the first column, i.e 2nd-1st, 3rd-2nd etc
```
awk '{print $1-prev;prev=$1}' num.dat 
```

##### Exercise 3
```
## cheap solution
awk '{print $1+$NF,$0}' task2.dat
```

```
## 3.1 Write a one-line awk script to calculate the occupied space in this folder. (*)
ls -l | awk '{sum =sum+$5} END{print sum }'
```

```
## 3.2 Modify the script to count only the files in your home directory (hopefully you have some in your home folder)(hint: directories begin with ”d” in the access field) (*)

ls -l | awk '{ if ($1 !~ /^d/) sum =sum+1} END { print sum}'
```

```
## Write a one-line awk script to add 1 to each number in the second column. (*)
awk_seminar$] awk '{print $1,$2+1,$3}' coord.dat 

## Modify the script to multiply all numbers by factor of 1.8897 . 
awk '{print 1.8897*$1,1.8997*$2,1.8897*$3}' coord.dat 
 
awk 'BEGIN {fac = 1.189} {print fac*$1,fac*$2,1.fac*$3}' coord.dat 
```