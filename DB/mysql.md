# MySql

## B树结构

`BTree`又叫做多路平衡搜索树，一颗m叉的`BTree`特性如下：

* 树种每个节点最多包含m个孩子
* 除根节点和叶子结点外，每个节点至少有`ceil(m/2)`个孩子
* 若根节点不是叶子结点，则至少有两个孩子
* 所有的叶子结点都在同一层
* 每个非叶子结点由n个key与n+1个指针组成，其中`ceil(m/2)-1 <= n <= m-1`

## 常用命令

```mysql
// 连接服务器
mysql -h localhost -P 3306 -u root -p

// 显示数据库
SHOW DATABASES;

// 创建数据库
CREATE DATABASE [IF NOT EXISTS] db_name [DEFAULT] CHARACTER SET utf8mb4;

// 删除数据库
DROP DATABASE [IF EXISTS] db_name;

// 选择数据库
USE database_name;

// 获取一个数据库中的表
SHOW TABLES;

// 显示一个表的所有列
SHOW COLUMNS FROM table_name;
或者
DESCRIBE table_name;

// 显示服务器状态
SHOW STATUS;

// 用来显示创建特定数据库和表的语句
SHOW CREATE DATABASE db_name;
SHOW CREATE TABLE table_name;

// 显示授予用户的安全权限
SHOW GRANT;

// 显示错误信息或者警告信息
SHOW ERRORS;
SHOW WARNINGS;
```

## 检索数据

```mysql
// 读取表的某列
SELECT col_name FROM tab_name;
```

## 排序检索

**关键字`ORDER BY`**

```mysql
// 按某行排序
SELECT prod_name FROM products ORDER BY prod_name;

// 按多个列排序，先按prod_price排序，如果price相同再按prod_name排序
SELECT prod_id, prod_price, prod_name FROM products ORDER BY prod_price, prod_name;

// 指定排序方向。默认排序方向是升序，指定降序关键词为DESC
SELECT prod_id, prod_price, prod_name FROM products ORDER BY prod_price DESC, prod_name;
// DESC 关键字只应用于直接位于其前面的列名。如果想在多个列上降序排列，则需要在每个列名后添加DESC
```

## B树和B+树区别
