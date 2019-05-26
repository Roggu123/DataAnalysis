Table of Contents
=================

   * [Concept](#concept)
      * [1.1 基础入门概念](#11-基础入门概念)
         * [1.1.1 各种数据库的定义](#111-各种数据库的定义)
         * [1.1.2 数据库和Excel相比的优势](#112-数据库和excel相比的优势)
         * [1.1.3 数据库管理工具有何异同](#113-数据库管理工具有何异同)
         * [1.1.4 参考](#114-参考)

# <center>Concept</center>
学习数据分析当中一些概念的总结分析



## <div id="11-基础入门概念">1.1 基础入门概念</div>
### <div id="111-各种数据库的定义">1.1.1 各种数据库的定义</div>    
数据库：保存有组织的数据的容器（通常是一个文件或一组文件）；  
数据库管理工具(DBMS)：数据库是通过DBMS创建和操纵的容器，经过衡量对比，作为初学者的我选用DBeaver；  
数据库对比（篇幅有限只比较三种主流数据库）：  

|		  |Oracle			|MySQL		 |SQL Server|   
|-------- |:---------:    |:-----:        |:-----:        |    
|应用场景：	|				   |               |               |  
|大型数据库：<br>海量数据、高吞吐量、<br>复杂逻辑、高计算量，<br>以及高可用性|传统行业的数据<br>化业务，对可用<br>性、健壮性、<br>安全性、实时性、<br>海量数据存储<br>分析要求极高||windows生态<br>系统的产品,<br>高度集成化，<br>缺IT人才的<br>中小企业，会<br>偏爱SQL Server|
|非大型数据库：||应用实例大都集<br>中于互联网方向,<br>高并发存取能力<br>并不比大型数据<br>库差，同时价格<br>便宜，安装使用<br>简便快捷||
|架构（执行）：|具有文件管理的<br>统一性，在SQL<br>执行优化方面非<br>常好|可自由选择存储<br>引擎，每个表都<br>是一个文件，都<br>可以选择合适的<br>存储引擎，这种<br>开放插件式的存<br>储引擎导致文件<br>的一致性大大降<br>低。在多表关联<br>、子查询优化、<br>统计函数等方面<br>是软肋|工作过程跟Oracle<br>是非常相似的|
|总结：|**价格不菲，但功<br>能齐全**|**体积小、速度快<br>成本低，开放源<br>码**|**使用最方便、开<br>发最方便、运维<br>最方便**|  
### <div id="112-数据库和Excel相比的优势">1.1.2 数据库和Excel相比的优势</div>  
>两个完全不同的东西，某些内容有重叠，都有行列，都可筛选数据。  
但数据库存储的**数据量**远大于Excel；  
数据库要存入**结构化数据**，Excel随意；  
数据库支持的**用户数**远大于Excel；  
数据库只能实现数据的**存储和取出**，Excel可以实现**计算功能**；  
  
### <div id="113-数据库管理工具有何异同">1.1.3 数据库管理工具有何异同</div>  

|		  |Oracle			|MySQL		 |SQL Server|DB2|SQLite|优点|缺点|   
|--------|:---------:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|     
|Toad|	支持|支持|支持|未知|未知|数据比较，架构比较，复制移动数据库|App Store中国区没有|  
|DBeaver|支持|支持|支持|支持|支持|支持数据库多还免费，[更多](https://sspai.com/post/44247)|未知|
|DataGrip|支持|支持|支持|支持|支持|大众评价高，语句提示好，更加工程化|收费，数据导入功能弱|
|workbench|未知|支持|未知|未知|未知|非常适合MySQL|比较复杂|
|Navicat系列|支持|支持|支持|未知|支持|直觉化的图形界面|非教育机构人员收费|  


### <div id="114-参考">1.1.4 参考</div>  
[1] 熊腾焱. [SQL Server 和 Oracle 以及 MySQL 有哪些区别？](https://www.zhihu.com/question/19866767/answer/13625499)  
[2] 知乎. [数据库是什么？它与 Microsoft Excel 有什么区别？](https://www.zhihu.com/question/24250613)  
[3] howtoing. [SQLite、MySQL、PostgreSQL：比较关系数据库管理系统](https://www.howtoing.com/sqlite-vs-mysql-vs-postgresql-a-comparison-of-relational-database-management-systems)  
[4] HideOnAnnie. [介绍一款替代SSMS的sqlserver管理工具 toad for sqlserver5.7](https://blog.csdn.net/xingfuniunan/article/details/9176637)