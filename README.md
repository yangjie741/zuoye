# 2.23
不可以，指针是否有效还不知道

# 2.24
因为lp的类型不是int，而void定义了一个空指针，可以接受任意类型的对象。

# 2.25
1. ip是一个int类指针型的，i是一个int型的变量，r是一个int型的引用。
2. i是一个int型的变量，ip是一个空指针。
3. ip是一个int类型的指针，ip2是一个int类型的变量。

# 2.35
第一个auto  j  类型为int
第二个auto  &k 类型为const int &
第三个auto *p类型为const int *
第四个auto j2类型为const int
第五个auto &k2 类型为const int&

# 3.4
```
#include <iostream>
#include <string>
using namespace std;
void main()
{	
	string mystring1 , mystring2;
	cin>>mystring1>>mystring2;
	if (mystring1 != mystring2)
	{
		cout<<(mystring1 >= mystring2 ? mystring1 : mystring2)<<endl;
	}
	
}
```

# 3.5
```
#include <iostream>
#include <string>
using namespace std;
void main()
{	
	string mystring;
	string sumstring;
	while (getline(cin ,mystring))
	{
		sumstring += mystring;
		cout<<sumstring<<endl;
	}
}
```
```
#include <iostream>
#include <string>
using namespace std;
void main()
{	
	string mystring;
	string sumstring;
	while (getline(cin ,mystring))
	{
		sumstring = sumstring+mystring+" ";
		cout<<sumstring<<endl;
	}
}
```

# 3.23
```
#include <iostream>
#include <string>
#include <vector>
using namespace std;
void main()
{	
	vector<int> text(10,5);
	for (auto it = text.begin(); it != text.end();it++)
	{
		*it = *it * 2;
		cout<<*it<<endl;	
	}
}
```
# 6.10
```
#include <iostream>
#include <string>
#include <vector>
using namespace std;
 
int exchange(int &val1, int &val2)
{
	int a;
	a = val1;
	val1 = val2;
	val2 = a;
	return 0;
}
void main()
{	
	cout<<"请输入需要交换的两整数:";
	int val1,val2;
	cin>>val1>>val2;
	cout<<"交换之前的两数："<<val1<<" "<<val2<<endl;
	exchange(val1,val2);
	cout<<"交换之后的两数："<<val1<<" "<<val2<<endl;
}
```

# 6.19
(a). 函数只有一个参数，传入两个不合法

(b). 合法

(c). 合法

(d). 合法

# 6.39
(a). 错误，只是重复生命了

(b). 错误

(c). 正确

# 7.16
访问说明符的作用域是开始知道下一个访问说明符或者类结束。不想被使用该类的程序看到的代码细节，都要private.

# 7.27
返回引用的函数为左值，返回*this的函数，返回本函数修改后的对象本身而非对象的副本。这样的话就会出现函数的重复使用
```
myScreen.move(4, 0).set('#').display(std::cout);
//move()和display()函数可以相互调用，因为他们的返回值是对象的本身，该对象就是myScreen,move()和dispaly()函数对myScerrn执行不同的操作
```

# 7.49

(a). 合法 
(b). 不合法，Salesdata&类型与Salesdata类型之间不可转换 
(c). 不合法，const不对，因为combine本身是需要改变传入参数的

# 7.58
```
// example.h
class Example {
public:
    static double rate;   //不能直接初始化
    static const int vecSize = 20;
    static vector<double> vec;
};
// example.C
#include "example.h"
double Example::rate = 6.5;
vector<double> Example::vec(Example::vecSize); 
```
