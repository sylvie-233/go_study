# websocket

> Author: Sylvie233
>
> Date: 24/05/01

## 基础介绍






## 核心内容

```
websocket:
	CloseMessage:
	Conn: 连接对象
		Close():
		PongHandler():
		ReadJSON():
		WriteMessage():
	Dialer:
		Dial():
	TextMessage:
	Upgrader: http协议升级
		ReadBufferSize:
		WriteBufferSize:
		Upgrade():
```