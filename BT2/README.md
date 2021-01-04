# 💻 Phân tích và Thiết kế thuật toán CS112.L12.KHCL
## Week 2 "Seaweed":

![](https://portal.uit.edu.vn/Styles/profi/images/logo186x150.png)

---
- **Contributors**

	- Trần Minh Tiến - 18521492

	- Đinh Duyên Bảo Duy - 18520658

	- Trần Tuấn Vỹ - 18520406

----
1. Abstraction: Find the n(2k+1) element in a Fibonacci sequence where k is the index/ position in the *modified* Fibonacci sequence and n is the start element of that *modified* Fibonacci sequence
2. Pattern Recognition: Find an element in a Fibonacci sequence
3. Algorithm design(s):
 - **Approach 1:** Space optimized Fibonacci.
	 - For example, plain recursion solution takes a lot of time and space, because it travels through unnecessary nodes in order to get to the destination node:
 ![](https://hiringfor.tech/assets/images/posts/2020-10-26-my-resources-for-dynamic-programming.png)
	 - As we can see, red nodes are unnecessarily travelled through, finding F(5) requires F(4) and F(3), F(4) requires F(2) and F(3), that is two times of F(3) in one recursion so that processing time and space would be exponentially increased.
	 - To solve this problem, we implement dynamic programming solution on this particular case to remove abundant steps, the solution will be dynamic programming with bottom up method.
	 - We simply store all the previous values in an array and calculate later values using solved ones.
	 - For example, we know that in a Fibonacci sequence, F(0) = 0 F(1) = 1 and F(n) = F(n-1) + F(n-2) for n > 1 and n is the position of the value in the sequence. Therefore, to minimize calculation, we store the values of F(n-1) and F(n-2) after every iteration to solve F(n), store F(n) then after another iteration, F(n) becomes F(n-1), F(n-1) becomes F(n-2) and so on.
	 ![](https://i.imgur.com/yThh6bR.png)
	 - We don't have to call every 2 same values every node we want to solve.
- **Dynamic programming**
```
Input:
	n: int, the value of the initial element
	k: int, the number of cycles or generations
Output:
	ans: int, the value of the element after k cycles or generations
Initialization:
	arr: int, array (arr[0], arr[1],...), an unmodified and limited Fibonacci sequence
Temporary variable(s):
	temp: int, index of the required element in the unmodified and limited Fibonacci sequence
Condition(s):
	n: 1 <= n <= 1000
	k: 1 <= k <= 10^18
	temp: 1 <= temp and temp = 2 * k + 1
Pseudocode:
	function modified_Fibonacci(n, k) is
		temp := 2 * k + 1
		initialize arr with temp + 1 elements
		arr[0] := 0
		arr[1] := 1
		for i := 2 to temp:
			arr[i] = arr[i-1] + arr[i-2]
		end loop
		return n*arr[temp]
Time complexity: O(k) (elements are generated (2k+1) times)
```
 - **Approach 2:** Matrix for Fibonacci.
 	- Applying matrix to the problem:\n
![matrix.png](data:image/png;base64,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)\n
