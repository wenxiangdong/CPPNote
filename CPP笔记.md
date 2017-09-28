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
* ​
