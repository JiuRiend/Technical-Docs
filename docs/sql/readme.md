免费的、轻量级的关系型数据库

## 安装
服务器端安装软件，要求系统必须是“干净”, 有问题的同学可以先重装一下系统、或者恢复电脑出场设置

## 功能
- 增 insert 增加一条或多条数据/记录
- 删 delete 删除一条或多条数据/记录
- 改 update 修改一条或多条数据/记录
- 查 select 查询一条或多条数据/记录

## 查询语句

```md
select * from <table>  去某一张表查询所有数据
select * from <table> where id=1 去某一张表精确查询某一条或多条记录
select * from <table> limit [start,count] 去某一张表查询所有数据字段，返回指定数据
```

## 插入语句
```md
inset into <table> (`key1`,`key2`) VALUES ('val1','val2');
```

## heidsql
mysql数据的图形可视化操作界面，方便开发