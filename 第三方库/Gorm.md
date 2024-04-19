# Gorm基础

> Author: Sylvie233
>
> Date: 24/04/17


## 基础介绍


加载数据库驱动

新建表名为结构体名小写复数形式







## 核心内容

```yaml
gorm:
	Association:
		Find(): 输出查询
	DB:
		Association():
		Close(): 关闭数据库
		Create(): 添加数据
		CreateTable(): 创建表
		Count():
		Debug():
		Delete(): 删除数据
		DropTable(): 删除表
		Exec():
		First(): 第1条数据
		Group():
		HasTable(): 表存在
		Having():
		Joins(): 连接
		Limit():
		LogMode():
		Model(): 选择模型
		Not(): 
		Offset():
		Or():
		Order():
		Preload(): 预加载（默认执行关联查询）
		Raw():
		Scan():
		Select():
		Table(): 选择表
		Update(): 更新数据
		Where(): 条件
	Model:
		ID:
		CreatedAt:
		DeletedAt:
		UpdatedAt:
	Open(): 打开数据库

```




### gorm标签

```
gorm:
	-: 忽略
	AUTO_INCREMENT:
	column:
	default:
	
	index:
	not null:
	primary_key:
	size:
	type:
	unique: 
	--- 关联tag
	AssociationForeignKey:
	ForeignKey:
	many2many:
```



### 一对一关联


三种关联查询方式
- Assocaition
- Preload
- Related



### 一对多关联



### 多对多关联





