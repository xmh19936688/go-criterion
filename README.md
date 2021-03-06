* 有人用你做的东西，会不会想骂你  
* 有人接手你的代码，会不会想骂你  

[toc]

# 数据一致性
* 如果同一字符串或数值在代码中出现第二次且表示相同含义，则应该为其定义常量

# 代码复用

# 参数与返回值
宽进严出原则  
若无合理理由，禁止interface{}作为参数  
若无合理理由，禁止interface{}作为返回值  
如果返回值包含指针类型，最好是返回空结构体指针而不是nil  
```go
res, err := cli.List()
return res.Data, err
// 若List方法第一个返回值类型为指针，当实现代码保证返回值不为nil时，调用时的代码就可以如此简化
```

# 命名规范

## 同一缩写
例如client缩写为cli，那么所有类似地方都缩写为cli。如果缩写为c，那么同意缩写为c。

## 驼峰
除非特殊情况，尽量不在命名中使用下划线

## 约定缩写
临时变量：`t` `tmp`
返回值/结果：`res`

## 介词使用

### of
通常用于“某物的某属性”，如`GetInfoOfBean`获取bean的info

### from
通常用于“从”，如`GetDataFromDB`从DB获取data

### for
通常用于“为某物做某事”，如`GenKeyForRecord`为record生成key

### by
通常用于“根据”或“通过”，如`GetBeanByID`根据ID获取bean

### log规范
1. log分级：fatal、error、warning、info、debug  
2. 支持分级输出：可以指定输出某一级别以上的log，比最高级更高的级别表示不输出log  
3. 关键字最好在日志信息的开始，便于在vim或其他编辑器中搜索时，减少列抖动。如`failed to xxxx`或`error: xxxx`

# error处理
1. 如无合理理由，每个error返回值必须处理或返回给调用者。  
2. 不建议既处理又返回。  
3. 不建议既输出又返回。

# 其他
1. 文件以空行结束
2. 文件最外层代码块之间需要有空行，内层代码块视情况而定
3. 组织import（分组与排序）
4. 提交代码前，清理无效代码
5. 如果if中有return，则该if不允许有else或else-if
