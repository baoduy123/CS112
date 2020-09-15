# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## BT1 "BOT":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

+Trần Minh Tiến - 18521492

+Đinh Duyên Bảo Duy - 18520658

+Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Tìm dãy các phần tử liên tiếp trong mảng sao cho có tổng lớn nhất.
2. Pattern Recognition: Kadane’s Algorithm, Dynamic Programing
3. Algorithm designed:
```
Input: 
	n: int,(1<=n<=10^6)
	array[n]: array (array[0], array[1], array[2], ..., array[n-1])
	p: int
	q: int
Output: q: beginning index of the max sum continuous array
	p: ending index of the max sum continuous array
	ans: max sum of the max sum continuous array
Temporary Initialization:
	ans:= min(array) ,int
	sum:= 0, int	

def MaxSumConArray(n, array)
	Loop for i from 0 to n-1 of the array:
	(1)	sum = sum + array[i]

	(2)	if (ans < sum) {
	(2.1)		ans = sum
	(2.2)		p = i
		}
		
	(3.1)	if (sum < 0) {
			sum = 0
	(3.2)	} else {
			q = i
		}
		
	(4)	i = i+1
	End loop
	return p, q, ans
```
