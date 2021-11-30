[toc]

## 一、容器与函数记录

### 1、qsort 快速排序函数

```
声明： void qsort(void* base,size_t num,size_t width,int(__cdecl*compare)(const void*,const void*)); 
参数： 1 待排序数组，排序之后的结果仍放在这个数组中
　　　 2 数组中待排序元素数量
　　　 3 各元素的占用空间大小（单位为字节）
　　   4 指向函数的指针，用于确定排序的顺序（需要用户自定义一个比较函数）
```

```
// 用法案列：对一个整形数组排序
qsort(pArray, nLength, sizeof(int), compare);

int compare(const void* num1, const void* num2) {
	return *(int*)num1 - *(int*)num2;
}
```



### 2、for(a:b) 在列表和数组时遍历

```
int pArray[] = {3,5,1,2,4};

for(int i : pArray) {
    printf("%d ", i);
}
```



### 3、list 链表容器

```
// 声明
std::list<int> container;
// 添加数据
container.push_back(num);
// 弹出数据
container.pop_back(num);
```

```
// 删除参数是迭代器指针
container.erase(curIte);

// 用迭代器迭代后删除当前节点
list<int>::iterator curIte = container.begin();
while(curIte != container.end()) {
    static int num = 0;
    if (num++ == 3) {
        container.erase(curIte);
        break;
    }
    ++curIte;
}
```



### 4、约瑟夫环公式和解法

```
长度为n的环，每次删除第m个数，求最后剩下的那个数字
f(n,m)={ 0                n = 1
      ={ [f(n-1,m)+m]%n   n > 1
```

```
int LastRemaining(unsigned int n, int m)
{
    if(n < 1 || m < 1)
        return -1;
    int nLastNumber = 0;
    for (int i = 2; i < n; ++i) 
        nLastNumber = (nLastNumber + m) % i;   
    return nLastNumber;
}
```



### 5、unordered_set  无序集容器

无序集是一种容器，它以不特定的顺序存储惟一的元素，并允许根据元素的值快速检索单个元素

```
std::unordered_set<char> set; // 定义

size_t count(const key_type& k)	//返回哈希桶中关键码为k的键值对的个数
insert(n)	//向容器中插入键值对
erase(n)	//删除容器中的键值对

bool empty() const	检测unordered_set是否为空
size_t size() const	获取unordered_set的有效元素个数
iterator find(const key_type& k)	返回k在哈希桶中的位置

void clear()	清空容器中有效元素个数
void swap(unordered_set&)	交换两个容器中的元素
size_t bucket_count()const	返回哈希桶中桶的总个数
size_t bucket_size(size_t n)const	返回n号桶中有效元素的总个数
size_t bucket(const key_type& k)	返回元素key所在的桶号
```



### 6、string 字符串

```
// 返回该字符的位置
int pos = str.find('X')
<<<<<<< HEAD

str.size() //求长度 
=======
str.size()
```



### 7、判断字符是否是字母或数字

```
isalpha 是否为字母
	islower 是否为小写字母
	isupper 是否为大写字母
isdigit 是否为数字
isalnum 是否为字母或数字
```



### 8、stack 栈操作

```
// 创建
std::stack<list*> nodes; 

// 获取栈顶
list* pTop = nodes.top();

// 压入和弹出
nodes.push(data);
nodes.pop();

// 空
nodes.empty();
```



### 9、queue 队列操作

```
// 创建
std::queue<int> que; 

 // 大小
que.size()

// 获取第一个
int pre = que.front()；
```

