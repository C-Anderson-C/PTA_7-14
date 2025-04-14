# PTA_7-14
# 求整数段和
# 给定两个整数A和B，输出从A到B的所有整数以及这些数的和。

# 输入格式：输入在一行中给出2个整数A和B，其中−100≤A≤B≤100，其间以空格分隔。

# 输出格式：首先顺序输出从A到B的所有整数，每5个数字占一行，每个数字占5个字符宽度，向右对齐。最后在一行中按Sum = X的格式输出全部数字的和X。
```cpp
#include<iostream>
#include<iomanip>
using namespace std;
int main() {
	int A, B;
	cin >> A >> B;
	if (A<-100||B>100||A>B) {  //判断输入是否合法
		cout << "Error" << endl;
		return 0;
		}
	int sum = 0;
	int count = 0;
	for (int i = A;i <= B;i++) {
	

		cout << setw(5) << right << i;
		sum += i;
		count++;  //计数器来计算是否这行有5个数，有就换行
		if (count % 5 == 0) {
			cout << endl;
		}
	}
	if (count % 5 != 0) {  //最后一行手动换行
		cout << endl;
	}
	cout << "Sum = " << sum << endl;  //记得要有空格
	return 0;
}