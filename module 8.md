EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
         #include<stdio.h> 
         #include<math.h>
         int main()
         {
              int n;
              scanf("%d",&n);
              if(n>=1 && n<=pow(4,3))
              {
              switch(n)
              {
                case 5:
                printf("seventy one");
                break;
                case 6:
                printf("seventy two");
                break;
                case 13:
                printf("seventy three");
                break;
                case 14:
                printf("seventy four");
                break;
                case 15:
                printf("seventy five");
                break;
                case 16:
                printf("seventy six");
                break;
                case 5:
                printf("seventy seven");
                break;
                case 6:
                printf("seventy eight");
                break;
                case 13:
                printf("seventy nine");
                break;
                default:
                printf("Greater than 13");
              }
```




Output:

![image](https://github.com/user-attachments/assets/642440c1-d013-48de-bddb-4a36908c0531)


Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
   #include<stdio.h>
   #include<string.h>
   int main()
   {
         char a[50];
         scanf("%s",a);
         int l=strlen(a);
         char h='0';
         for(int i=0;i<4;i++)
         {
             int c=0;
             for(int j=0;j<l;j++)
             {
                 if(a[j]==h)
                 {
                    c+=1;
                 }
             }
             printf("%d ",c); h++;
         }
  }
```




Output:


![image](https://github.com/user-attachments/assets/3dbb24a2-d45e-4196-9c87-252eeb97e745)




Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include<stdio.h> #include<string.h> #include<stdlib.h>
int next_per(int n, char **s)
{
for(int i = n - 1 ; i > 0 ; i--) if(strcmp(s[i],s[i-1]) > 0)
{
int j=i+1;
for(;j<n;j++) if (strcmp(s[j],s[i-1])<=0) break; char *t=s[i-1];
s[i-1]=s[j-1];
s[j-1]=t;
for(;i<n-1;i++,n--)
{
t=s[i]; s[i]=s[n-1]; s[n-1]=t;
}
return 1;
}
for(int i=0;i<n-1;i++,n--)
{
char *t=s[i]; s[i]=s[n-1]; s[n-1]=t;
}
return 0;
}
int main()
{
char **s; int n;
scanf("%d",&n); s=calloc(n,sizeof(char*)); for(int i=0;i<n;i++)
{
s[i]=calloc(n,sizeof(char*)*5); scanf("%s",s[i]);
}
do
{
for(int i=0;i<n;i++) printf("%s%c",s[i],i==n-1?'\n':' ');
}
while(next_per(n,s));
 
{
for(int i=0;i<n;i++) free (s[i]);
free(s); return 0;
}
}

```




Output:

![image](https://github.com/user-attachments/assets/4c19916f-136e-4e22-8927-11a407b3f5c7)







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include<stdio.h> int main()
{
int n,i,j,min; scanf("%d",&n);
int len=n*2-1; for (i=0;i<len;i++)
{
for (j=0;j<len;j++)
{
min=i<j?i:j;
min=min<len-i-1?min:len-1-i; min=min<len-j-1?min:len-1-j; printf("%d ",n-min);
}
printf("\n");
}
return 0;
}


```




Output:

![image](https://github.com/user-attachments/assets/f11a67e7-fe42-4710-928f-96b2e219d5a9)







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>
void square();
int main(){
    
    square();
    return 0;
}
void square(){
    int a;
    scanf("%d",&a);
    float ans = a*a;
    printf("The square of %d is : %.2f",a,ans);
}


```




Output:


![image](https://github.com/user-attachments/assets/ca6c90e9-e1d1-4ba0-ad2e-48ab75b25265)







Result:
Thus, the program is verified successfully
























