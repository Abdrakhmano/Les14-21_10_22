### Task №1(8kyu)

Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.

[Task_link](https://www.codewars.com/kata/5547929140907378f9000039)

#### Solution

~~~ Java
public class Kata {
    public static String shortcut(String input) {
        String[] glas = {"a", "e", "o", "i", "u"};
        for (int i = 0; i < glas.length; i++) {
            input = input.replace(glas[i], "");
        }
        return input;
    }
}
~~~

#### Fav Solution

~~~ Java
public class Kata {
  public static String shortcut(String input) {
    return input.replaceAll("[aeuio]", "");
  }
}
~~~

### Task №2(7kyu)

ASC Week 1 Challenge 4 (Medium #1)

Write a function that converts any sentence into a V A P O R W A V E sentence. a V A P O R W A V E sentence converts all the letters into uppercase, and adds 2 spaces between each letter (or special character) to create this V A P O R W A V E effect.

Note that spaces should be ignored in this case.

Examples
~~~ Java
"Lets go to the movies"       -->  "L  E  T  S  G  O  T  O  T  H  E  M  O  V  I  E  S"
"Why isn't my code working?"  -->  "W  H  Y  I  S  N  '  T  M  Y  C  O  D  E  W  O  R  K  I  N  G  ?"
~~~

[Task_link](https://www.codewars.com/kata/5966eeb31b229e44eb00007a)

#### Solution

~~~ Java
public class Solution{
    public static String vaporcode(String s) {
        String result = "";
        String str = s.replace(" ", "");
        String[] str1 = str.split("");
        for (int i = 0; i <= str1.length - 1; i++) {
            str1[i] = str1[i].toUpperCase();
            if (i == str1.length - 1) {
                result = result + str1[i];
            } else {
                result = result + str1[i] + "  ";
            }
        }
        return result;
    }
}
~~~

#### Fav Solution

~~~ Java
public class Solution {
  public static String vaporcode(String s) {
    String y;
        
    y = s.replaceAll(" ", "").replaceAll("", "  ").toUpperCase();
    return y.substring(2,y.length()-2);
  }
}
~~~


### Task №3(8 kyu)
This Kata is intended as a small challenge for my students

All Star Code Challenge #18

Create a function that accepts 2 string arguments and returns an integer of the count of occurrences the 2nd argument is found in the first one.

If no occurrences can be found, a count of 0 should be returned.
~~~ Java
("Hello", "o")  ==>  1
("Hello", "l")  ==>  2
("", "z")       ==>  0
~~~
Notes:

The first argument can be an empty string
The second string argument will always be of length 1

[Task_link](https://www.codewars.com/kata/5865918c6b569962950002a1)

#### Solution

~~~ Java
public class CodeWars {
    public static int strCount(String str, char letter) {
        int count = 0;
        for (int i = 0; i <= str.length() - 1; i++) {
            if (str == "") {
                return 0;
            } else if (str.charAt(i) == letter) {
                count++;
            }
        }
        return count;
    }
}
~~~

#### Fav Solution

~~~ Java
public class CodeWars {
  public static int strCount(String str, char letter) {
    return (int)str.chars().filter(x -> x == letter).count();
  }
}
~~~


### Task №4(7 kyu)

Are the numbers in order?
In this Kata, your function receives an array of integers as input. Your task is to determine whether the numbers are in ascending order. An array is said to be in ascending order if there are no two adjacent integers where the left integer exceeds the right integer in value.

For the purposes of this Kata, you may assume that all inputs are valid, i.e. arrays containing only integers.

Note that an array of 0 or 1 integer(s) is automatically considered to be sorted in ascending order since all (zero) adjacent pairs of integers satisfy the condition that the left integer does not exceed the right integer in value.

For example:
~~~ Java
isAscOrder(new int[]{1,2,4,7,19}) == true
isAscOrder(new int[]{1,2,3,4,5}) == true
isAscOrder(new int[]{1,6,10,18,2,4,20}) == false
isAscOrder(new int[]{9,8,7,6,5,4,3,2,1}) == false // numbers are in DESCENDING order
~~~

N.B. If your solution passes all fixed tests but fails at the random tests, make sure you aren't mutating the input array.


[Task_link](https://www.codewars.com/kata/56b7f2f3f18876033f000307/train/java)

#### Solution

~~~ Java
public class Solution {
    public static boolean isAscOrder(int[] arr) {
        for (var i = 0; i < arr.length - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                return false;
            }
        }
        return true;
    }
}

~~~

#### Fav Solution

~~~ Java
import java.util.Arrays;

public class Solution {

    public static boolean isAscOrder(int[] arr) {
        int[] copyArr = Arrays.copyOf(arr, arr.length);
        Arrays.sort(copyArr);
        
        return Arrays.equals(copyArr, arr);
    }

}

~~~


##### Comment:
Пропустила одно занятие по болезни, поэтому сдаю 4 номера:)
