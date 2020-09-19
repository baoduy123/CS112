# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## Week 1 "BOT":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

---
- **Contributors**

	- Trần Minh Tiến - 18521492

	- Đinh Duyên Bảo Duy - 18520658

	- Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Find the maximum contiguous subarray
2. Pattern Recognition: Kadane’s Algorithm
3. Algorithm design(s):
**Dynamic Programing**
```
Input:
	n: int, number of elements of the array
	array: int, array (array[0], array[1], array[2], ..., array[n-1])
Output:
	q: int, beginning index of the max sum contiguous array
	p: int, ending index of the max sum contiguous array
	ans: int, max sum of the max sum contiguous array
Initialization:
	q:= 0, int
	p:= 0, int
Temporary variable(s):
	temp:= 0, int, temporary best start for the contiguous array which has the best sum
	ans:= -inf, int, temporary best sum for the contiguous array
	sum:= 0, int, temporary sum for the the contiguous array
Condition(s):
	n: 1 <= n <= 10^6
	arr: 0 <= arr[i] <= 10^9, 0 <= i <= n-1

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
