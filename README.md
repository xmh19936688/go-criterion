* 有人用你做的东西，会不会想骂你  
* 有人接手你的代码，会不会想骂你  

[toc]

# 数据一致性
* 如果同一字符串或数值在代码中出现第二次且表示相同含义，则应该为其定义常量

# 代码复用

# 函数返回值
宽进严出原则  
尽量不用interface{}作为返回值类型

# 命名规范

## 同一缩写
例如client缩写为cli，那么所有类似地方都缩写为cli。如果缩写为c，那么同意缩写为c。

## 驼峰
除非特殊情况，尽量不在命名中使用下划线

## 介词使用

### of
通常用于“某物的某属性”，如`GetInfoOfBean`获取bean的info

### from
通常用于“从”，如`GetDataFromDB`从DB获取data

### for
通常用于“为某物做某事”，如`GenKeyForRecord`为record生成key

### by
通常用于“根据”或“通过”，如`GetBeanByID`根据ID获取bean

# log规范
1. 区分模式：debug或release区分log的打开与关闭
2. log分级：fatal、error、warning、info、debug

# error处理
1. 如无合理理由，每个error返回值必须处理或返回给调用者。  
2. 不建议既处理又返回。  
3. 不建议既输出又返回。

# 其他
1. 文件以空行结束
2. 文件最外层代码块之间需要有空行，内层代码块视情况而定
3. 组织import（分组与排序）
4. 提交代码前，清理无效代码
