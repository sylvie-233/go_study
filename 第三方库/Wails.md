
# Wails


> Author: Sylvie233
>
> Date: 24/05/01


## 基础介绍

### wails

```
wails:
	build:
	dev:
	doctor: 环境检查
	init: 创建项目
		-n:
		-t:
```


### wails.json

```
wails.json:
	$schema:
	name:
	outputfilename:
```

## 核心内容

```
wails:
	notify:
		Alert():
		Notify():
	options:
		App:
			Bind:
			Height:
			OnStartup:
			Title:
			Width:
	runtime:
		EventsEmit():
		EventsOff():
		EventsOn():
		EventsOnce():
		WindowExecJs(): 执行js脚本
		WindowSetTitle():
	systray:
		IMenu:
			ShowMenu():
		AddMenuItem():
		Run():
		SetIcon():
		SetTitle():
		SetTooltip():
		SetOnClick():
	windows: 窗口程序工具
		MessageBox():
wailsjs:
	EventsEmit(): 事件触发
```




### 函数绑定

go语言绑定函数生成js文件`wailsjs`


#### 事件监听



### 系统功能

#### Window



#### Menu


#### Browser



#### Clipboard


#### Screen


