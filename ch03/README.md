# Chapter 3

## 3.22

>     // Error: Invalid operands to binary expression ('iterator(aka '__wrap_iter<int *>') and 'iterator')
>     vector<int>::iterator mid = (vi.begin() + vi.end()) / 2;

There is not an existed operator for adding two iterators together.

## 3.23

> `bitset<64> bitvec(32)`

64 位，第 5 位为 1，其他为 0

> `bitset<32> bv(1010101)`

32 位，十进制 1010101 等于 二进制 0 0000 0000 0000 1111 0110 1001 1011 0101
 
> `string bstr; cin >> bstr; bitset<8> bv(bstr);`

8 位，将输入的字符串从右至左的 8 个字符对 bv 的 0~7 位进行初始化

# Chapter 4

## 4.1

假设 get_size 是一个没有参数并返回 int 值的函数，下列哪些定义是非法的？为什么？

>
````
unsigned buf_size = 1024;
int ia[buf_size]
````

非法，因为 buf_size 不是 const 变量

> `int ia[get_size()]`

非法，因为 get_size() 是函数调用，不是常量表达式，不能用于定义数组的维数。

> `int ia[4 * 7 - 14]`

合法

> `char st[11] = "fundamental"`

非法，因为字符数组后面会添加空字符，应该改为 `st[12]`。

## 4.2

> 下面数组的值是什么？

````
// 元素类型为 string 的数组，将各元素初始化为空字符串
string sa[10];
// 在函数体外定义的数组，各元素初始化为 0
int ia[10];
int main() {
	// 元素类型为 string 的数组，将各元素初始化为空字符串
	string sa2[10];
	// 在函数体内定义的数组，各元素未初始化，值不确定
	int ia2[10];
}
````

## 4.3

> `int ia[7] = {0, 1, 1, 2, 3, 5, 8};`

合法

> `vector<int> ivec = {0, 1, 1, 2, 3, 5, 8};`

错误，不能这样初始化 vector。

> `int ia2[] = ia1;`

错误，不能用一个数组来初始化另一个数组。

> `int ia3[] = ivec;`

错误，不能用 vector 对象来初始化数组。

## 4.5

使用 vector 的优点：

- 数组不提供 push_back 或其他方法在数组中添加新元素。
- vector 更加灵活，且可以复制和赋值等操作，更易于调试。

> C++ 11 添加了 `std::array<>` 来减少 vector 某些操作的花销，固定大小的数组可以避免堆在分配内存或被销毁时所产生的额外花销。

## 4.6

应改为：

````
for (size_t ix = 0; ix < array_size; ++ix)
	    ia[ix] = ix;
````

## 4.7
