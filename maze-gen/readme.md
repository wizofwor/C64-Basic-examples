##MAZE-GEN

BASIC MAZE GENERATOR

![image](https://github.com/wizofwor/C64-Basic-examples/blob/master/maze-gen/capture.png?raw=true)

### Explanations

```
30 gosub 200 
```
jumps to the subroutine to plot to indicator bar


```
40 p = 5 : q = 205.5
```
sets initial parameters


```
60 rem random maze generator
70 for i=1104 to 1635 : poke i,q+rnd(1)
80 get k$ : if k$<>"" then gosub 310
90 next
```
Plots the maze pattern up to indicator, usind the famous `poke 205.5 + rnd(1)` trick. We are cheking the key press with `get k$` and if there is a key press were jumping to a subrutine to evaluate the keypress with `if k$<>"" then gosub 310`.


```
100 for i=1651 to 2024 : poke i,q+rnd(1)
110 get k$ : if k$<>"" then gosub 310
120 next
```
Same loop to plot the maze pattern after the indicator

```
130 goto 60
190 end
```
loop back

```
200 rem indicator bar
210 for i=0 to 14 : read a : poke 1636+i,a : next
250 for i=0 to 14 : read a : poke 55908+i,a : next
290 return
```
Subroutine to plot indicator bar using data row starting form line 500
First loop is to put characters. Second loop is for colors.

```
300 rem key control 
310 if k$=chr$(133) then p=p-1
320 if k$=chr$(134) then p=p+1
```
Maze pattern will be determinad via varible p. F1 key `chr$(133)` decrease the value while F3 key `chr$(134)` increases.

```
330 if p<0 then p=0
340 if p>10 then p=10
```
P should stay withing 0-10

```
350 q = 205 + p/10
```
Remember the trick POKE 205.5 + rnd(1) we will play with the first decimal place to change probability. Thats way our magic number is q = 205 + p/10 

```
360 rem update indicator bar
370 for j = p+1 to 11 : poke 1637+j,100 : next
380 for j = 1 to p+1 : poke 1637+j,224 : next
390 return
```
This part is updating the indicator bar to display current value of p

```
490 rem char and color data for indicator bar
500 data 134,177,224,224,224,224,224,224
510 data 100,100,100,100,100,134,179
520 data 10,10,1,1,1,1,1,1
530 data 1,1,1,1,1,7,7
```
Finally the data part used by indicator bar subroutine at line 200