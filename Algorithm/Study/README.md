**# ❗ 개인 정리**



<br>



<br>



**## 목차**

> - [순열](#순열)
>
> > - [순열 기본](#순열-기본)
> > - [순열 비트마스킹](#순열-비트마스킹)



<br>

<br>

---

<br>

> # 순열
>
> > ## 순열 기본
> >
> > > - 순열 (Permutation)
> > >
> > > > - 서로 다른 것들 중 몇 개를 뽑아서 한 줄로 나열하는 것
> > > > - 서로 다른 n개 중 r개를 택하는 순열 👉 nPr
> > > >
> > > > > - nPr = n * (n-1) * (n-2) * ... * (n-r+1)
> > > > > - nPn = n! = 팩토리얼
> > > >
> > > > - n = 12일 때, 순열의 수 👉 4억 7천만
> > > >
> > > > ```
> > > > import java.util.Arrays;
> > > > import java.util.Scanner;
> > > > 
> > > > public class Permutation_basic {
> > > >     //nPr
> > > >     static int n, r;
> > > >     static int[] input, selectedNumbers;
> > > >     static boolean[] isSelected;
> > > > 
> > > >     public static void main(String[] args) {
> > > >         Scanner sc = new Scanner(System.in);
> > > >         n = sc.nextInt();
> > > >         r = sc.nextInt();
> > > > 
> > > >         input = new int[n];
> > > >         selectedNumbers = new int[r];
> > > >         isSelected = new boolean[n];
> > > > 
> > > >         for(int i = 0; i<n;i++){
> > > >             input[i] = sc.nextInt();
> > > >         }
> > > > 
> > > >         permutation(0);
> > > >     }
> > > > 
> > > >     public static void permutation(int numberOfDraws){
> > > >         if(numberOfDraws == r){
> > > >             System.out.println(Arrays.toString(selectedNumbers));
> > > >             return;
> > > >         }
> > > > 
> > > >         for(int i = 0; i < n ; i++){
> > > >             if(isSelected[i]) {
> > > >                 continue;
> > > >             }
> > > > 
> > > >             selectedNumbers[numberOfDraws] = input[i];
> > > >             isSelected[i] = true;
> > > >             permutation(numberOfDraws+1);
> > > >             isSelected[i] = false;
> > > >         }
> > > >     }
> > > > }
> > > > ```
> >
> > <br>
> >
> > ## 순열 비트마스킹
> >
> > > - 정수와 비트 연산자를 사용하여 순열 생성