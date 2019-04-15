<font size="4" color="red">**本教程SQL文件：**<a href="https://github.com/guxuepo/MyBlog/blob/master/Mysql%E9%9B%86/1_Mysql%E4%B9%8B%E6%9C%80%E5%85%A8%E5%AD%90%E6%9F%A5%E8%AF%A2%E6%95%99%E7%A8%8B/Mysql%E5%AD%90%E6%9F%A5%E8%AF%A2%E4%B9%8B%E6%A1%88%E4%BE%8BCode.sql">**点击查看**</a></font>

## 一、子查询基本概念代码
<font  >  导入本节教程的sql文件运行一下实例代码：</font>
<br>
<img src="https://github.com/guxuepo/MyBlog/blob/master/Mysql%E9%9B%86/1_Mysql%E4%B9%8B%E6%9C%80%E5%85%A8%E5%AD%90%E6%9F%A5%E8%AF%A2%E6%95%99%E7%A8%8B/img/1_%E5%AD%90%E6%9F%A5%E8%AF%A2%E4%B9%8B%E5%9F%BA%E6%9C%AC%E6%A6%82%E5%BF%B5%E4%BB%A3%E7%A0%812.png?raw=true" alt="子查询基本概念代码">
**以上代码执行结果如图：**
<img src="https://github.com/guxuepo/MyBlog/blob/master/Mysql%E9%9B%86/1_Mysql%E4%B9%8B%E6%9C%80%E5%85%A8%E5%AD%90%E6%9F%A5%E8%AF%A2%E6%95%99%E7%A8%8B/img/%E5%AD%90%E6%9F%A5%E8%AF%A21.png?raw=true" alt="子查询基本概念代码结果图片">

此时，子查询所在的上“上层查询”，就称为主查询（一个查询可以有多个子查询，类似多重for循环）
也可以说：子查询是为主查询的某个部分提供数据的查询。
上一条实例代码中，括号中的子查询查出了产地是‘北京’的所有商品的平均价
最终看就是：select * from product where price > 某个数 
**如图：**
<img src="https://github.com/guxuepo/MyBlog/blob/master/Mysql%E9%9B%86/1_Mysql%E4%B9%8B%E6%9C%80%E5%85%A8%E5%AD%90%E6%9F%A5%E8%AF%A2%E6%95%99%E7%A8%8B/img/%E5%AD%90%E6%9F%A5%E8%AF%A22%E5%8C%97%E4%BA%AC%E5%B9%B3%E5%9D%87%E4%BB%B7.png?raw=true" alt="北京商品平均价图片">

## 二、标量子查询

#### 含义：
   标量子查询就是指子查询的结果是“单个指”（一行一列）的查询。 

#### 使用：
   标量子查询通畅用在where子句中，作为主查询的一个条件判断数据。
   本质是上，标量子查询的结果，就可以直接当做“一个值”来使用

### 标量子查询小题目:
<font style="color:red">找出所有奢饰品！奢饰品的定义为：其价格超过贵重物品的平均价!
</br>贵重品的定义为：超过所有商品的平均价！</font>

#### 标量子查询题目答案：
<img src="" alt="标量子查询题目答案图片">

**运行结果**
<img src="" alt="标量子查询答案运行结果">

  
## 三、列子查询  

#### 含义：
列子查询出的结果为“一列数据”，类似这样的：  
select pinpai from product where chandi = '北京';
结果为：
<img src="" alt="一列数据查询结果">

#### 使用：
列子查询通常用在where子句的in运算符中，代替in运算符的“字面值”列表数据。  
比如：  
<img src="" alt="where子句的in运算符">
  
## 四、子查询的特定关键字
#### in关键字  
in关键字在子查询中主要用在列子查询中代替人为手工罗列出来多个“字面值”数据。  

之前的in我们是这样用的：select * from product where chandi in('北京','上海')  
北京and上海这写关键字都是手写的需要改成子查询语句就可以了

#### any关键字
any关键字用在比较操作操符的后面，表示查询结果的多个数据中的任一个满足该比较操作符就算满足。  
代码栗子:<span style="color:red">找出在北京生产的但价格比在深圳生产的任一商品贵的商品<span/>

<img src="" alt="any关键字代码栗子">


### all关键字
all关键字用在比较操作操符的后面，表示查询结果的多个数据中的所有都满足该比较操作符才算满足。

## 小总结

**子查询只是在wher后面继续写select语句而已，更加扩展了查询的范围**