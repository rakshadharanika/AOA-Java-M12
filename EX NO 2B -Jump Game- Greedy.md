
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 19.9.25
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. If the array length is ≤ 1 or the first element is 0, return -1 (cannot move).

2. Initialize three variables: far = 0 → farthest index reachable, end = 0 → end of current jump range, jump = 0 → number of jumps made

3. Loop from i = 0 to n - 2 and update far = max(far, i + nums[i]).

4. When i reaches end, increment jump and update end = far.

5. After updating, if end >= n - 1, break the loop (last index reachable).

6. Return jump if end reaches last index, otherwise return -1. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: V RAKSHA DHAEANIKA
Register Number: 212223230167
*/
import java.util.Scanner;

public class MinJumpToEnd {

   
    public static int minimumJumps(int[] nums) {
        if(nums.length<=1) return -1;
        if(nums[0]==0) return -1;
        int far=0,jump=0,end=0;
        for (int i =0;i<nums.length-1;i++)
        {
            far=Math.max(far,i+nums[i]);
            if(i==end)
            {
                jump++;
                end=far;
                if(end>=nums.length-1) {
                    break;
                }
                if(end==i) return -1;
            }
        }
     return end>=nums.length-1?jump:-1;  
    }

   
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}

```

## Output:

<img width="876" height="407" alt="image" src="https://github.com/user-attachments/assets/9f8663a0-659d-4beb-ab18-f9293bd44ea0" />


## Result:
The program successfully implemented and the expected output is verified.
