# Gin框架

> Author: Sylvie233
>
> Date: 22/12/26
> Point:	
> 	【golang-web开发】gin框架手把手教学：P12

## 基础介绍

Gin、Beego、Iris

安装

```
"github.com/gin-gonic/gin"
```


## 核心内容

```
gin:
	Context:
		Abort():
		DefaultPostForm():
		DefaultQuery():
		GetHeader(): 获取请求头
		GetQuery():
		GetRawData(): 获取原始请求体
		HTML(): 响应HTML数据
		JSON(): 返回JSON数据
		MultipartForm(): 可获取文件数据
		MustGet():
		Next():
		Param(): 获取param参数
		PostForm(): 获取表单参数
		Query(): 获取query参数
		QueryArray():
		QueryMap():
		Redirect(): 重定向 
		Set():
		String(): 返回字符串数据
		XML(): 返回XML数据
		YAML(): 响应YAML数据
	Error:
	Engine: 引擎（继承RouterGroup）
		Default():
		GET(): get路由注册
		Handle(): 路由处理函数
		LoadHTMLFiles(): 加载html文件
		LoadHTMLGlob(): 
		New():
		NoRoute():
		POST(): post路由注册
		Routes():
		Run(): 框架运行
		StaticFile(): 配置静态文件挂载
		StaticFS(): 配置静态目录挂载
		Use():
	H: （本质是一个map[string]any）
	HandlerFunc:
	HandlersChain:
	IRouter:
	Iroutes:
	LogFromatter:
	LoggerConfig:
	Param:
	ResponseWriter:
	RouteInfo:
	RouterGroup:
	RoutesInfo:
```

框架结构类似koa2












### 模板引擎


























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

