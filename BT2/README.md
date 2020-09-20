# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## Week 2 "Seaweed":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

---
- **Contributors**

	- Trần Minh Tiến - 18521492

	- Đinh Duyên Bảo Duy - 18520658

	- Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Find an odd element in a *modified* Fibonacci sequence
2. Pattern Recognition: Find an element in a Fibonacci sequence
3. Algorithm design(s):
- **Dynamic programming**
```
Input:
	n: int, the value of the initial element
	k: int, the number of cycles or generations
Output:
	sum: int, the value of the element after k cycles or generations
Initialization:
	n1 := 1, first number of Fibonacci
	n2 := 1, second number of Fibonacci
	sum := 0, the next number of Fibonacci
Condition(s):
	n: 1 <= n <= 1000
	k: 1 <= k <= 10^18
	mod: 1e9+7, modified number
Pseudocode:
	function modified_Fibonacci(n, k) is
		n1 := 1
		n2 := 1
		sum := 0
		mod := (1e9+7)
		
		for i := 1 to 2*k+1:
		if (i==1): 
			sum = 1
		else:
			sum = n1+n2
			n1 = n2
			n2 = sum
		end loop
		
		return (sum * n % mod)
```
