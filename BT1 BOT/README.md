# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## BT1 "BOT":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

+Trần Minh Tiến - 18521492

+Đinh Duyên Bảo Duy - 18520658

+Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Find the maximum contiguous subarray
2. Pattern Recognition: Kadane’s Algorithm, Dynamic Programing
3. Algorithm designed:
```
Input: 
	n: int, (1<=n<=10^6)
	array: int, array (array[0], array[1], array[2], ..., array[n-1])
	p:= 0, int
	q:= 0, int
Output: q: beginning index of the max sum continuous array
	p: ending index of the max sum continuous array
	ans: max sum of the max sum continuous array
Temporary Initialization:
	temp:= 0, int, temporary best start for the contiguous array which has the best sum
	ans:= array[0], int
	sum:= 0, int, temporary sum for the the contiguous array

def MaxSumConArray(n, array)
	Loop for i from 0 to n-1 of the array:
	(1)	if (sum < 0) {
	(1.1)		temp = i
	(1.2)		sum = array[i]
		} else {
	(1.3)		sum = sum + array[i]
		}
		
	(2)	if (ans < sum) {
	(2.1)		ans = sum
	(2.2)		q = i
	(2.3)		p = s
		}
	
	(3)	i = i + 1
	End loop
	return p, q, ans
```
