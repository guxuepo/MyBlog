<font size="4" color="red">**本教程SQL文件：**<a href="https://github.com/guxuepo/MyBlog/blob/master/Mysql%E9%9B%86/1_Mysql%E4%B9%8B%E6%9C%80%E5%85%A8%E5%AD%90%E6%9F%A5%E8%AF%A2%E6%95%99%E7%A8%8B/Mysql%E5%AD%90%E6%9F%A5%E8%AF%A2%E4%B9%8B%E6%A1%88%E4%BE%8BCode.sql">**点击查看**</a></font>

## 一、子查询基本概念代码
<font background-color="rgb(85, 85, 85)">&nbsp;&nbsp;导入本节教程的sql文件运行一下实例代码：</font>
<font color="red" font-weight="bold">
```
#题目：大于北京产地的产品平均价的所有产品
select * from product where price > (
    #子查询北京所有产品的平均价
    select avg(price) from product where chandi='北京'
);
```
</font>
**以上代码执行结果如图：**
<img src="" alt="子查询基本概念代码结果图片">


此时，子查询所在的上“上层查询”，就称为主查询（一个查询可以有多个子查询，类似多重for循环）
也可以说：子查询是为主查询的某个部分提供数据的查询。
上一条实例代码中，括号中的子查询查出了产地是‘北京’的所有商品的平均价
最终看就是：select * from product where price > 某个数 如图


<img src="" alt="北京商品平均价图片">

## 二、标量子查询