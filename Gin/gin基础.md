# Gin框架

> Author: Sylvie233
>
> Date: 22/12/26

> 

[TOC]

## 基础介绍

Gin、Beego、Iris

安装

```
"github.com/gin-gonic/gin"
```











## Gin库

### Context

```
Context:
	Abort():
	GetRawData():
	HTML():
	JSON():
	MustGet():
	Next():
	Param():
	PostForm():
	Query():
	Redirect():
	Set():
```



### Engine

```
Engine:
	Default():
	LoadHTMLFiles():
	LoadHTMLGlob():
	New():
	NoRoute():
	Routes():
	Run():
	Use():
```



### gin

```
gin:
	Context:
	H:
	Default():
```



### IRouter

```
type IRouter interface {
	IRoutes
	Group(string, ...HandlerFunc) *RouterGroup
}
```



### IRoutes

```
IRoutees:
	GET():
	POST():
	PUT():
	Static():
```



### RouterGroup

```
RouterGroup:
	GET():
	Group():
	POST():
	PUT():
	Static():
```









