# Gin框架

> Author: Sylvie233
>
> Date: 22/12/26
> Point:	
> 

## 基础介绍

Gin、Beego、Iris

安装

```
go get -u "github.com/gin-gonic/gin"
```


## 核心内容

```
gin:
	Context:
		Request: 
		Writer:
		Abort(): 中断处理
		ClientIP():
		DefaultPostForm():
		DefaultQuery():
		File(): 响应文件数据
		FormFile(): 文件获取
		Get(): 请求域获取值
		GetHeader(): 获取请求头
		GetQuery():
		GetRawData(): 获取原始请求体
		Group(): 路由分组
		Header(): 响应头
		HTML(): 响应HTML数据
		JSON(): 返回JSON数据
		MultipartForm(): 可获取文件数据
		MustGet():
		Next(): 请求链式放行
		Param(): 获取param参数
		PostForm(): 获取表单参数
		Query(): 获取query参数
		QueryArray():
		QueryMap():
		Redirect(): 重定向 
		Routes(): 
		SaveUploadedFile(): 保存上传文件
		Set(): 请求域设置值
		ShouldBind(): 根据请求头类型获取参数
		ShouldBindJSON(): 参数绑定校验
		ShouldBindQuery():
		ShouldBindUri(): 
		String(): 返回字符串数据
		XML(): 返回XML数据
		YAML(): 响应YAML数据
	DefaultPrintRouteFunc:
	DefaultWriter:
	Error:
	Engine: 引擎（继承RouterGroup）
		Default():
		GET(): get路由注册
		Handle(): 路由处理函数
		LoadHTMLFiles(): 加载html文件
		LoadHTMLGlob(): 
		NoRoute():
		POST(): post路由注册
		Routes():
		Run(): 框架运行
		StaticFile(): 配置静态文件挂载
		StaticFS(): 配置静态目录挂载
		Use(): 全局中间件注册
	H: （本质是一个map[string]any）
	HandlerFunc:
	HandlersChain:
	IRouter:
	Iroutes:
	LogFromatter:
	LogFromatterParams:
		ErrorMessage:
		Method:  
		Path:
		StatusCode:
		TimeStamp:
		MethodColor():
		ResetColor():
		StatusCodeColor():
	LoggerConfig:
		Formatter:
		Output:
		SkipPaths:
	Param:
	ReleaseMod:
	ResponseWriter:
	RouteInfo:
		Handler:
		HandlerFunc:
		Method:
		Path:
	RouterGroup:
		GET():
		POST():
		Use(): 使用中间件
	RoutesInfo:
	Default():
	LoggerWithConfig():
	LoggerWithFormatter(): 日志中间件生成
	New():
	SetMode():
binding:
	Validator:
		Engine():
validator:
	FieldLevel:
		Field():	
	Validate:
		RegisterValidation(): 注册校验器
	ValidationErrors:
	Default(): 生成Engine
	Logger(): gin默认日志中间件
	New(): 生成Engine
	Recovery(): gin默认错误恢复中间件
```

框架结构类似koa2

Default()生成的Engine默认注册了Logger()、Recovery()两个中间件








### 路由




### 中间件








### 模板引擎








### 参数校验

参数绑定和校验

支持json、form、uri、

#### binding
```
binding:
	contains:
	datetime:
	dive:
	endswith:
	eq:
	eqfield:
	excludes:
	ip:
	len:
	max:
	min:
	ne:
	nefield:
	oneof: 枚举判断
	required:
	startswith:
	uri:
	url:
		msg: 错误信息
```



##### 自定义校验

```
func 校验函数（v validator.FieldLevel) bool {
	
}
```



















## 第三方库
```
gorm:
	logger:
		info:
		Default:
			LogMode():
		Interface:
	schema:
		NamingStrategy:
		Relationship:
	Association: 关联操作
		Append(): 关联追加数据
		Clear()):
		Count():
		Delete():
		Find():
		Replace():
	Config: 数据库连接配置
		Logger: 日志 
		NamingStrategy: 命名策略
		SkipDefaultTransaction:
	DB:
		*Config:
		Error:
		RowsAffected:
		Statement:
		getInstance():
		Assocaition(): 关联表
		AutoMigrate(): 迁移数据库
		Commit():
		Connection():
		Count():
		Create(): 创建
		CreateBatches():
		Debug():
		Delete(): 删除
		Distinct(): 去重
		Exec():
		Find(): 查询多条语句
		First(): 第一条数据
		Group(): 分组
		InnterJoins():
		Joins(): 联表查询（传入需要联表查询的字段名）
		Last(): 最后一条数据
		Limit(): 分页
		Model(): 选择模型
		Not(): 取反条件
		Offset(): 分页
		Or(): 或条件查询
		Order(): 排序
		Preload():
		Raw(): 原生sql
		Rollback():
		Save(): 支持更新
		Scan(): 数据保存实例
		Scopes(): 查询引用（SQL片段）
		Select(): 字段投影
		SetupJoinTable(): 自定义表连接（多对多中间表）
		Table(): 选择表
		Take(): 查询（默认主键）
		Update(): 更新
		Updates():
		Use():
		Where(): 条件查询（可嵌套子查询）
	ErrRecordNotFound:
	Migrator:
		AddColumn():
		AutoMigrate():
		CreateIndex():
		CreateTable():
		CurrentDatabase():
		DropColumn():
		GetTables():
		HasColumn():
		MigrateColumn():
		RenameColumn():
	
	Model:
		CreatedAt:
		DeletedAt:
		ID:
		UpdatedAt:
	Plugin: 插件
		Initialize(): 初始化函数
		Name():
	Session:
	Tx:
	Open():
casbin:
	persist:
		NewDBAdaper():
	util:
		RegexMatch():
	Enforcer:
		AddPolicy():
		Enforce(): 判断是否允许访问
		SavePolicy():
	NewEnforcer(): 创建一个casbin模型
logrus:
	Entry: 重要传参
		Buffer:
		Caller:
			File:
			Function:
			Line:
		Data: 用来传递数据的map
		Level:
		String():
		WithField():
		WithFields():
		 
	ErrorLevel:
	Hook:
		Fire(): 真正执行的地方
		Levels():
	JSONFormatter:
	Level:
	TextFormatter:
		ForceColors:
		FullTimestamp:
		TimestampFormat:
	WarnLevel:
	AddHook():
	Debugf():
	Error():
	GetLevel():
	Infof():
	SetFormatter():
	SetLevel():
	SetOutput():
	SetReportCaller():
	WithField(): 设置字段值
	Wranln():
```


### Gorm

#### tag
```
gorm:
	column: 字段名
	comment: 注释
	default:
	embedded: 嵌套字段
	embeddedPrefix: 嵌套字段前缀
	foreignKey: 外键（外表）
	index:
	joinForeignKey: 多对多外键(中间表中外表主键)
	joinReferences: 多对多外键(中间表中自身表主键)
	many2many: 多对多查询中间表
	primaryKey:
	references: 外键（自身表）
	size: 字段大小
	type: 字段类型
	unique:
```

#### Scope
查询引用，sql片段




#### Hook
```
hook:
	BeforeSave:  
	BeforeCreate:  
	AfterCreate  :
	AfterSave:

	Scan: 从数据库中读出来
	Value: 存入数据库

	MarshalJSON: json序列化
```


#### 联表
##### 预加载
数据库表中没有物理外键时，关联查询必须先预加载关联表
本质不是连表查询，而是多次查询然后拼接





##### 一对一




###### Belongs To
有一个对方对象，外键在自身对象中



###### Has One

有一个对方对象，外键在对方对象中



##### 一对多




###### Has Many
```golang
type Article struct {
	ID uint
	Title string
	UserID uint // 属于
	User user  `gorm:"foreignKey:UserID;references:ArticleID"` // 属于
}

type User struct {
	ID uint
	Name string
	Article []Article `gorm:"foreignKey:ID"`
}
```





##### 多对多

###### Many To Many



### Casbin

ACL、RBAC
subject、object、action
访问控制模型model、策略policy
model.conf、policy.csv（实际的权限控制列表）


PERM模型（Policy, Effect, Request, Matchers）
- Policy：定义权限的规则
- Effect：定义组合了多个Policy之后的结果
- Requset：访问请求
- Matcher：判断Request是否满足Policy



casbin默认支持文件存储访问控制策略，可使用adapter适配数据库存储
所有操作都是基于访问控制模型model





#### model.conf

```
```text
request_definition]
r = sub, obj, act

[policy_definition]
p = sub, obj, act

[role_definition]
g = _, _

[policy_effect]
e = some(where (p.eft == allow))

[matchers]
m = g(r.sub, p.sub) && r.obj == p.obj && r.act == p.act
```

- request_definition：表示访问控制请求的定义，包括sub（访问者）、obj（资源）和act（请求动作）。
- policy_definition：表示访问控制策略的定义，包括sub（访问者）、obj（资源）和act（请求动作）。
- role_definition：表示角色的定义。
- policy_effect：表示策略生效的条件。
- matchers：表示匹配器，用于判断是否满足规则。




### logrus

#### Formatter


#### Hook



