**Link:** https://leetcode.com/problems/find-the-winner-of-the-circular-game/description/?envType=daily-question&envId=2024-07-08
<br><br>
**Solution:**
![image](https://github.com/ShreyasiDebnath/Leetcode_daily/assets/92165807/77e0733f-fe0f-4960-ab1b-2f83368d2d38)
<br>
  1. we know that at the last index-0 person will win
  2. try to fine the position of winnier when there ar 2 person
  3. try to fine the position of winnier when there ar 3 person
  4.  try to fine the position of winnier when there ar n person
  5.  now we got the position of the winner <br>
  to calculate the previous winner position
<br>
***Alternative***:
<br>
We can use queue
<br>
1.frist enter all the n number into the queue<br>
2. pop k-1 element and pop the front (that is my kth elemet to remove)<br>
3. lastly when we left withonly one number int the queue that will be my answer<br>
