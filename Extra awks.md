##### Extraaa

##### Changing the delimiter from sapce to tab
```awk
awk -F " " '{print $1"\t"$2"\t"$3"\t"$4"\t"$5"\t"$6"\t"$7"\t"$8"\t"$9"\t"$10"\t"$11"\t"$12"\t"$13"\t"$14"\t"$15}' Common_variant_HT_LPK > tmp; mv tmp Common_variant_HT_LPK 
```
##### Exercise 1.2  
```shell
cut -f 1,2,4,5 Common_variant_HT_LPK | head
## Getting first, second and resepctive columns with tab delimited
```
