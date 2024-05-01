# go-zero

> Author: Sylvie233
>
> Date: 24/05/01


## 基础介绍


微服务组件
- 服务网关
- 服务发现
- 服务调用
- 服务监控
- 服务追踪
- 服务治理
- 基础设施：数据存储
- 分布式配置中心
- 分布式事务
- 定时任务
- 容器编排




最简实践：服务注册+api+rpc









### goctl

- api服务生成
- rpc服务生成
- model代码生成
- 模板管理

```
goctl:
	--version:
	api:
		new: 新建api服务
		go: 转换api文件（生成go代码）
		plugin: api插件
	docker:
	env:
		check:
			--force:
			--install:
			--verbose:
	kube:
	model:
		mysql: 
			ddl: 根据sql文件生成模型（生成go代码）
	rpc:
		new: 新建rpc调用
		protoc: 编译proto文件（生成go代码）
	template:
```



### api
`.api`文件可以帮助自动生成代码，类似`proto`


```
api目录结构：(自动生成)
	/etc:
		xxx-api.yaml: 项目配置文件
	/internal:
		/config: 配置类
			config.go:
		/handler: 路由处理函数
			routes.go: 路由配置
			xxxhandler.go:
		/logic: 逻辑层代码(实际业务：请求响应)
			xxxlogic.go:
		/svc: 服务Context上下文
			servicecontext.go:
		/types:
			types.go:
	xxx.api: api配置文件
	xxx.go:
```



#### api配置

```
// .api配置文件







```


##### type
类型定义

##### service
服务定义


###### @handler
服务方法定义

###### @doc
swag文档信息



##### @server
服务装饰定义
```
@server (
	prefix: api前缀 
	jwt: Auth （jwt校验）
)
```







### rpc
`proto`文件，远程服务调用配置




### model
模型文件生成







## 核心内容

```
go-zero:
	cache:
		Cache:
		CacheConf:
		Option:
	jwt:
		StandardClaims:
			ExpireAt:
		At():
		NewWithClaims():
		ParseWithClaims():
	logx:
		Logger:
	redis:
		RedisConf:
	rest:
		httpx: http工具包
			ErrorCtx():
			Parse():
			ParseJsonBody(): 请求参数解析
			SetErrorHandler():
			WriteJson():
		RestConf:
		Route: 路由
			Method:
			Path:
			Handler:
		MustNewServer():
		WithJwt():
		WithPrefix():
	sqlc:
		CachedConn:
	sqlx:
		SqlConn:
		NewMysql():
		NewSqlConn():
	zrpc:
		RpcClientConf:
		MustNewClient():
```

### Etcd

服务注册、发现







### gRPC

服务调用



### Prometheus
监控中间件


### Jaeger
链路追踪中间件



### DTM
分布式事务