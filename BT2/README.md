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
	 - We simply store all the previous values in a array and calculate later values using solved ones.
	 - For example, we know that in a Fibonacci sequence, F(0) = 0 F(1) = 1 and F(n) = F(n-1) + F(n-2) for n > 1 and n is the position of the value in the sequence so to minimize calculation, we store the values of F(n-1) and F(n-2) after every iteration then solve F(n), store F(n) then after another iteration F(n) becomes F(n-1), F(n-1) becomes F(n-2) and so on.
	 ![](https://i.imgur.com/yThh6bR.png)
	 - We don't have to call every 2 values every node we want to solve.
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
