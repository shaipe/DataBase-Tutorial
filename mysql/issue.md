Mysql 日志使用笔记
===
目录
- [获取当天数据]
### 1. 获取当天数据写法

#### 相关知识

**MySQL Date 函数**

下面的表格列出了 MySQL 中最重要的内建日期函数：

函数|描述
-|-
NOW()	|返回当前的日期和时间
CURDATE()	|返回当前的日期
CURTIME()	|返回当前的时间
DATE()	|提取日期或日期/时间表达式的日期部分
EXTRACT()	|返回日期/时间按的单独部分
DATE_ADD()	|给日期添加指定的时间间隔
DATE_SUB()	|从日期减去指定的时间间隔
DATEDIFF()	|返回两个日期之间的天数
DATE_FORMAT()	|用不同的格式显示日期/时间

#### 示例

```sql
-- 获取当天的第前10天的数据
select * from ord_order where date(AddTime) = DATE_SUB(CURDATE(),INTERVAL 10 DAY);
```