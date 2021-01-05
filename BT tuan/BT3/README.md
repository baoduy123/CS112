# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## Week 3 "H-Index":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

---
- **Contributors**

	- Trần Minh Tiến - 18521492

	- Đinh Duyên Bảo Duy - 18520658

	- Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Count the number of elements whose values are equal or higher than the number of elements in the array
2. Pattern Recognition: Travel a list or an array
3. Algorithm design(s):
```
Input:
	n: int, the number of elements in the array
	arr: int, array, the array which contains the elements
Output:
	h-index: int, the number of elements whose values are equal or higher than the number of element in the array
Temporary variable(s):
	length: int, the temporary number of elements
Condition(s):
	n: 1 <= n <= 5×10^5
	arr: arr[i], 0 <= i < n, 0 <= arr[i] <= 10^6
Pseudocode:
	function h-index(n, arr) is
		sort arr array descendingly
		initialize length to the number of elements in the arr array
		h-index := 0
		for i := 0 to n - 1:
			if arr[i] is greater than or equals to length - i:
				h-index = length - i
				break
		return h-index
Time Complexity: O(n logn) for sorting + O(n) for one loop = O(n logn)
```
