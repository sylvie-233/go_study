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
    install: 安装
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


通过匿名字段组合实现继承










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
	comparable: 可比较类型
```


#### 泛型约束




### Goroutine协程







### 模块

package包声明

main包：可执行程序













## 标准库
```
go standard:
	archive:
	bufio:
		Reader:
			Read():
			ReadByte():
			ReadLine():
		NewReader():
	builtin:
		append(): 添加元素（切片扩容）
		cap(): 容量
		close(): 关闭
		copy(): 拷贝
		len(): 长度
		make(): 引用内存分配
		print():
		println():
		string():
	bytes:
		Buffer:
			Bytes():
	cmp:
	compress:
	comtainer:
		heap:
		list:
		ring:
	context:
		Context:
			Done():
			Value():
		AfterFunc():
		WithCancel():
		WithTimeout():
		WithValue():
	crypto:
	database:
		sql:
			driver:
	debug:
	embed: 文件嵌入
	encoding:
		json:
			Marshal():
			Unmarshal():
	errors:
		Is(): 错误判断
		New(): 新建错误
	fmt:
		Print():
		Printf(): 格式化输出
		Println():
	hash:
	html:
		template:
			FuncMap:
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
			ReadFile():
			WriteFile():
		MultiWriter: 复合输出器
		Copy():
		ReadAll():
	log:
		slog:
		syslog:
		Println():
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
			Request:
			ResponseWriter:
			HandleFunc():
			ListenAndServe():
		rpc:
		url:
		Conn:
		TcpAddr: 
		TCPConn:
			Read():
			RemoteAddr():
			Write():
		TcpListener:
			AcceptTCP:
		DialTCP():
		Listen(): 监听
		ListenTCP():
		ResolveTCPAddr():
	os:
		exec:
		signal:
		user:
		File:
		Stdin: 标准输入流
		Stdout: 标准输出流
		Writer:	
		Create():
		MkdirAll(): 多级目录创建
		Open():
		OpenFile():
		ReadDir():
	path:
		filepath:
			Walk():
			WalkDir():
		Base():
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
		TypeOf(): 获取对象Type
	regexp:
		syntax:
	runtime:
	sort:
	strconv:
		Itoa():
		ParseInt():
	strings:
		Join():
	sync:
		atomic:
			LoadUnit32(): 原子获取值
			StoreUnit32(): 原子设置值
		Mutex:
			Lock():
			Unlock():
		Once: 只执行一次
			Do(): 
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


### 设计模式

```
设计模式：（23）
	创建型：（5）
		1.工厂方法模式：对于每一种具体的类型有个对应的工厂
		2.抽象工厂模式
		3.单例模式：饿汉、懒汉
		4.建造者模式：Builder
		5.原型模式：类似javascript的原型链
	结构型：（7）
		6.适配器模式
		7.装饰器模式：类似代理，实现统一个接口，持有具体实现（扩展方法，最终为接口类型）
		8.代理模式：代理实现同一个接口，持有具体实现
		9.外观模式
		10.桥接模式
		11.组合模式
		12.享元模式
	行为型：（11）
		13.策略模式
		14.模板方法模式
		15.观察者模式
		16.迭代器模式
		17.责任链模式
		18.命令模式
		19.备忘录模式
		20.状态模式
		21.访问者模式
		22.中介者模式
		23.解释器模式
```

