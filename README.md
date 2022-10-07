### Task 7kyu:

You are provided with an array of positive integers and an additional integer n (n > 1).
Calculate the sum of each value in the array to the nth power. Then subtract the sum of the original array.

[Task link](https://www.codewars.com/kata/58aed2cafab8faca1d000e20/train/java)

#### Solution:
```
import java.io.*;
public class Kata {
  public static int modifiedSum(int[] array, int power) {
    int sum1 = 0;
    int sum2 = 0;
    for(int i = 0; i < array.length; i++){
      sum1 += Math. pow(array[i], power);
      sum2 += array[i];
    }
    return sum1-sum2;
  }
}
```

#### Fav solution:
```
public class Kata {
  public static int modifiedSum(int[] array, int power) {
    int sum = 0;
    for (int i : array)
      sum+=Math.pow(i,power)-i;
    return sum;
  }
}
```

#### Comment:
Interestingly, the cycle was recorded, I did not immediately think of subtracting the elements of the cycle.


### Task 7kyu:

Given three integers a ,b ,c, return the largest number obtained after inserting the following operators and brackets: +, *, ()
In other words , try every combination of a,b,c with [*+()] , and return the Maximum Obtained.

[Task link](https://www.codewars.com/kata/5ae62fcf252e66d44d00008e/train/java)

#### Solution:
```
public class Kata
{
    public static int expressionsMatter(int a, int b, int c)
    {
       int[] array = new int[7];
       array[0] = a + b + c;
       array[1] = a + b * c;
       array[2] = (a + b) * c;
       array[3] = a * (b + c);
       array[4] = a * b * c;
       array[5] = a * c + b;
       array[6] = a * b + c;
       int maxValue = 0;
       for(int i = 0; i < 7; i++){
         if (array[i]>maxValue) maxValue = array[i];
       }
       return maxValue;
    }
}
```

#### Fav solution:
```
public class Kata
{
    public static int expressionsMatter(int a, int b, int c)
    {
      return  Math.max(Math.max(a + b + c, a * b * c),Math.max ((a + b) * c, a * (b + c)));
    }
}
```

#### Comment:
It was possible to do without the introduction of an array.
