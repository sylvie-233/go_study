# Go基础

> Author: Sylvie233
>
> Date: 22/12/26
>
> Point：
> 	


## 基础介绍

2009年



环境变量:GOROOT、GOPATH



GoLand开发工具









### go

```
go命令:
	build:
	clean:
		-modcache: 模块缓存
    env: 环境变量
    	-w: 设置环境变量
    get:
    	-u:
    install:
    mod:
    	init:
    	tidy:
    run: 运行
	version: 版本
	
```









## 基础语法

### 变量

注释：

```
//

/**/
```



变量定义：

```
var xxx type = xxx
xxx := xxx
```



匿名变量：

```
_
```



数据类型：

- 布尔
- 数值
- 字符串
- 指针
- 数组
- 结构体
- 通道
- 切片
- 函数
- 接口
- Map



数据类型转换





string字符串

字符串拼接：+



数组、切片



map



### 常量

const定义

iota常量计数，从0开始









### 关键字

```
关键字：
	any:
	bool:
	byte:
	defer:
	float32:
	float64:
	func:
	int:
	int64:
	nil:
	range:
	rune:
	select:
	string:
	uint8:
	uintptr:
	var:
```







### 表达式

```
表达式：
	
```







### 控制语句







### 函数

func关键字

```
func _函数名(参数列表) 返回类型 {}
```



main函数入口

数组传参为值拷贝





### 结构体











### Channel通道







### 泛型

泛型函数定义

```
func 函数名[T string|int,](xxx T) {}
```



泛型类型

```
type Slice[T int | float32] []T

类型:
	any:
	comparable:
```



### Goroutine协程







### 模块

package包声明

main包：可执行程序













## 标准库
```
go standard:
	archive:
	bufio:
	builtin:
		append(): 添加元素（切片扩容）
		cap(): 容量
		close(): 关闭
		copy(): 拷贝
		len(): 长度
		make(): 引用内存分配
		string():
	bytes:
	cmp:
	compress:
	comtainer:
		heap:
		list:
		ring:
	context:
	crypto:
	database:
		sql:
			driver:
	debug:
	encoding:
		json:
			Marshal():
			Unmarshal():
	errors:
		Is(): 错误判断
		New(): 新建错误
	fmt:
		Print():
		Println():
	hash:
	html:
	image:
	io:
		fs:
			DirEntry:
				Name():
				Info():
			FileInfo:
				IsDir():
				Size():
			WalkDirFunc:
		ioutil:
		Copy():
		ReadAll():
	log:
		slog:
		syslog:
	maps:
	math:
	mime:
		multipart:
			File:
				Close():
				ReadAll():
			FileHeader:
				Filename:
				Size:
				Open():
			Form:
				File:
	net:
		http:
		rpc:
		url:
	os:
		exec:
		signal:
		user:
		File:
			
		Create():
		Open():
		ReadDir():
	path:
		filepath:
			Walk():
			WalkDir():
	reflect:
		Ptr:
		Struct:
		StructField:
			Anonymous:
			Name:
			Offset:
			Tag: tag标签
			Type:
			IsExported():
		StructTag:
			Get():
		Type:
			Elem(): 指针取值
			Kind():
			NumField():
		TypeOf():
	regexp:
		syntax:
	runtime:
	sort:
	strings:
		Join():
	sync:
		atomic:
		Mutex:
			Lock():
			Unlock():
		RWMutex:
		WaitGroup:
			Down():
			Wait():
	testing:
		fstest:
		iotest:
		quick:
	text:
		scanner:
		template:
	time:
		After():
		Now():
	unsafe:
		Sizeof():
```


### bufio

```
bufio:
	
```



### builtin

```
builtin内建:
	append():
	close():
	delete():
	len():
	make():
	panic():
	recover():
```



### bytes

```
bytes:
	NewBuffer():
	NewReader():
```



#### Reader

```
Reader:
	
```







### context

```
context:
```





### encoding

#### binary

```
binary:
	LittleEndian:
	Read():
	Write():
```



#### json

```
json:
	Unmarshal():
```



### errors

```
errors:
	New():
```





### fmt

```
fmt:
	Print():
	Printf():
	Println():
		%b: 二进制
		%p: 地址
		%T: 类型
	Scan():
	Scanf():
	Scanln():
	Sprintf():
```



### io

```
io:
	ReadFull():
```



#### ioutil

```
ioutil:
	ReadFile():
```





### net 

```
net:
	Dial():
	Listen():
	ListenTCP():
	ResolveTCPAddr():
```





#### http

```
http:
	StatusMovedPermanently:
	
```



#### TCPAddr

```
TCPAddr:
	
```



#### TCPConn

```
TCPConn:
	Close():
	Read():
	Write(): 
```





#### TCPListener

```
TCPListener:
	AcceptTCP():
```





### log

```
log:
	Fatalf():
```





### os

```
os:
	
```



### sync

```
sync:
	RWMutex:
```



#### RWMutex

```
RWMutex:
	Lock():
	RLock():
	RUnlock():
	Unlock():
```





### testing

```
testing:
	T
```



#### T

```
T:
	
```





### time

```
time:
	Second:
	Sleep():
```



 

## 补充知识

