## 一、针对现有的数据库反向生成models
```
python manage.py inspectdb > models.py
```

## 二、Django使用原生sql

- 注意：使用原生sql的方式主要目的是解决一些很复杂的sql不能用ORM的方式写出的问题。

- extra：结果集修改器-一种提供额外查询参数的机制

- raw:执行原始sql并返回模型实例


```
1.使用extra：查询人民邮电出版社出版并且价格大于50元的书籍

Book.objects.filter(publisher__name='人民邮电出版社').extra(where=['price>50'])

2.使用raw
books=Book.objects.raw('select * from hello_book')
for book in books:
   print book

3.自定义sql
from django.db import connection
 
cursor = connection.cursor()
cursor.execute("insert into hello_author(name) VALUES ('郭敬明')")
cursor.execute("update hello_author set name='韩寒' WHERE name='郭敬明'")
cursor.execute("delete from hello_author where name='韩寒'")
cursor.execute("select * from hello_author")
cursor.fetchone()
cursor.fetchall()


上述方法是设置中如果有多个数据库，会默认使用 default，当你想使用指定的数据库连接时，引入的对象就变成了连接！

from django.db import connections
with connections['db1'].cursor() as cursor:

```
## 三、操作ORM
```

```
