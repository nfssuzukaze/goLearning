### 1. 常量

#### 1. 常量使用关键字 `const` 声明

```go
const limit = 512
const top uint16 = 1421
const Pi float64 = 3.1415926
const x, y int = 1, 3 // 多重赋值
```

`Go` 的常量定义可以限定常量类型（在变量名之后添加类型说明即可指定类型），但也不是必需的。如果定义常量的时候没有指定类型，那么该常量就是无类型常量，也叫字面常量

当需要设置多个常量的时候，不必重复使用 `const` 关键字，可以使用以下语法：

```go
const (
	num1 = 0
    num2 = 1
    num3 = 2
)
```

`Go` 语言还预定义了这些常量：`true` , `false` , `itoa`

`itoa` 是一个**可以被编译器修改**的常量，在 `const` 关键字出现时被重置为 0 ，在下一个 `const` 出现之前，每出现一次 `itoa` ，其所代表的数字自动加 1

```go
const (
	a = iota // a == 0
    b = iota // b == 1
    c = iota // c == 2
)

const d = iota // d == 0
```



### 2. 变量

`Go` 语言引入了关键字 `var` 对变量进行声明，也可以使用 `:=` 来对变量直接进行初始化（ `:=` 左侧的变量不能是已经被声明过的，否则会导致编译器错误）

```go
var num1 int = 1
var str string = "hello world"
var float float64 = 2.3
var v1 = 5 // 由编译器自动推断出 v1 的类型
v2 := 6 // 由编译器自动推断出 v2 的类型

v1, v2 = v2, v1 // 交换 v1 和 v2 的值
```



### 3. 数据类型

#### 1. 整形

+ `byte`
+ 补码表示的整形
  + `int`
    + 在不同平台下的位数不同，可以是 32 位，也可以是 64 位
  + `int8`
  + `int16`
  + `int32`
  + `int64`
  + `rune`
    + 等同于 `int32`
+ 无符号整形
  + `uint`
    + 在不同平台下的位数不同，可以是 32 位，也可以是 64 位
  + `unit8`
  + `uint16`
  + `unit32`
  + `uint64`
+ `uintptr`

通过 `unsafe.Sizeof()` 函数可以查看一个数据的字节长度

#### 2. 浮点型

+ `float32`
+ `float64`
+ `complex32`
+ `complex64`

#### 3. 布尔类型

布尔类型不支持自动或者强制的类型转换