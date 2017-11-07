# CPP笔记

### scope

- 程序级
- 文件级
  - 全局变量加static
- 函数级
- 块级

将接口放入.h文件，起到一定的封装作用

### 生命周期

- main中变量有全周期

### namespace

- using-declaration
  - using L::k;
- using-directive
  - using namespace L;

### 预处理

* symbolic constants    *constant*

* open subroutines    *inline*

* generic subroutines    *template*

  * `#denfine max(a,b) (a)>(b)?(a):(b)`
  * `#define mu(a,b) (a)*(b)`

* amazing code

  * `#define Conn(x,y) x##y`
    `#define ToChar(x) #@x`
    `#define ToString(x) #x`

### 数组

* 一维数组的传递，必须显式传递长度
* char数组（字符串）可以不传长度
* ` typedef int T[3]`
  ` 理解为 typedef int[3] T `
* 数组名就是代表所有数据的空间
  * 相当于代表对几亩地的所有权，在传递参数的时候，转换为指针传递，相当于用地契传递


### 指针

* 函数指针
  *  `int (*f)(int i)`
  *  `int *f(int i)`

### 引用

* 返回值是引用或指针时，只返回调用者传递的内容



## OOP

### 成员初始化表

* 按成员变量声明秦顺序
* 如果成员变量有对象，且要使用非默认构造方法初始化对象，只能在成员初始化表初始化，因为构造函数无法显式调用
* const 成员也只能在初始化表
* 顺序先于构造函数

### 动态对象

* new delete
* malloc free 
  * **不调用**构造和析构函数

### const成员

* 函数不能修改任何变量，除了 mutable变量

### 友元

* 访问其他类的私有变量，绕过get函数提高效率

### 继承

* 将子类赋值给父类，会**丢失**子类派生的属性（不同于java可以重新转换回来）
  * 这里应该用 **指针** 进行操作（或者引用）
  *  `A *p_a = &b;`
* Early Binding
  * 依据对象类型静态调用
* Late Binding
  * 依据对象**实际类型**动态调用

### 虚函数

* 限制

  * 类的成员函数才可以是虚函数
  * 内联成员函数不能是虚函数
  * 构造函数不能
  * 析构函数往往是虚函数

* 用虚函数表实现

  * 在**对象内存空间**（头部）中含有指向虚函数表的指针

* 举例

  ` class A `
  ` { `

  `public: `
  `A() { f();}`
  `virtual void f();`
  `void g();`
  `void h() { f(); g(); }`
  ` };`
  `class B: public A`
  `{ public:`
  `void f();`
  `void g();`
  `};`

  ` B b;  // A::A()， A::f, B::B()`
  `A *p=&b;`
  `p->f(); //B::f`
  `p->g(); //A::g`
  `p->h(); //A::h, B::f, A::g`

* ​