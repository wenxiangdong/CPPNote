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

