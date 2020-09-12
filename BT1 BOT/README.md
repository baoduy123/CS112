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
Ban đầu gán tổng các dãy liền kề (ans): min(Mảng), tổng:= 0
Duyệt vòng lặp i từ 0->n:
		Tổng += phần từ Mảng thứ i
		Nếu ans < tổng => {
			ans := tổng
			p:= i
		}
		Nếu tổng < 0 => bỏ phần tử Mảng thứ i bằng cách gán lại tổng := 0 
		Ngược lại tổng >0 => { 
			q:= i
			tổng giữ nguyên
		}	
		Quay về vòng lặp với i++
```
Output: khoảng (q+1) đến (p+1) nếu p ‡ q, tổng dãy = ans