# Logrus基础

> Author: Sylvie233
>
> Date: 24/04/17


## 基础介绍



### 日志级别





### 日志格式

#### Formatter



### 日志输出

#### 文件日志



### 日志分割

#### 时间分割




### 日志Hook








## 核心内容

```yaml
logrus:
	Entry:
		Caller: 调用者信息
			File:
			Function:
			Line:
		Level:
		Message:
		Time:
	Fields:
	Formatter: 自定义格式化器
		Format(): 实现自定义输出
	Hook:
		Fire(): 传入Entry进行配置
		Levels(): 哪些日志级别会生效
	TextFormatter:
		ForceColors:
	AddHook():
	Error():
	GetLevel():
	Println():
	SetFormatter():
	SetLevel():
	SetOutput():
	SetReportCaller(): 携带调用者信息
	WithField():
