# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## Week 2 "Seaweed":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

---
- **Contributors**

	- Trần Minh Tiến - 18521492

	- Đinh Duyên Bảo Duy - 18520658

	- Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Find an element in a *modified* Fibonacci sequence
2. Pattern Recognition: Find an element in a Fibonacci sequence
3. Algorithm design(s):
- **Dynamic programming**
```
Input:
	n: int, the value of the initial element
	k: int, the number of cycles or generations
Output:
	ans: int, the value of the element after k cycles or generations
Initialization:
	arr: int, array (arr[0], arr[1],...), a unmodified and limited Fibonacci sequence
Temporary variable(s):
	temp: int, index of the required element in the unmodified* and limited Fibonacci sequence
Condition(s):
	n: 1 <= n <= 1000
	k: 1 <= k <= 10^18
	temp: 1 <= temp <= 2 * k + 1
Pseudocode:
	function modified_Fibonacci(n, k) is
		temp := 2 * k + 1
		initialize arr with temp + 1 elements
		arr[0] := 0
		arr[1] := 1
		for i := 0 to temp:
			arr[i] = arr[i-1] + arr[i-2]
		end loop
		return n*arr[temp]
```
