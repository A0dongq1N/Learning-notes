# C++智能指针

> 智能指针的头文件为<memory>

## shared_ptr

### 小例子

```c++
shared_ptr<int> p1;   //p1可以指向一个int
shared_ptr<double> p2(new int(42))；   //p2执行一个值为42的int
```

### 初始化

- 智能指针的构造函数是`explicit`的，所以必须使用直接初始化的形式来初始化一个智能指针

```c++
shared_ptr<int> p1 = new int(42); //错误
shared_ptr<int> p2(new int(42));  //采用直接初始化方式初始化
```

- 同样的一个场景是，一个返回`shared_ptr`的函数的返回值也不能隐式的转化为一个普通的指针

```c++
//错误的做法
shared_ptr<int> fun(int p)
{
    return new int(p) //这里是一个普通的指针
}

//正确的做法
shared_ptr<int> fun(int p)
{
    return shared_ptr<int> (new int(p));
}
```

## unique_ptr

> 同一时刻，只能有一个`unique_ptr`指向一个给定对象

### 初始化

- 只能采用直接初始化的方式进行初始化

```c++
unique_ptr<int> p1(new int(12));
```

- 不支持不同的拷贝和赋值

```c++
unique_ptr<int> p1(new int(12));
unique_ptr<int> p2=p1;   //错误的
unique_ptr<int> p2(p1);  //错误的
unique_ptr<int> p3;
p3 = p1;                 //错误的
```









