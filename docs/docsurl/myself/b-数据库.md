

##  数据库

### 1 重置mysql数据库自增id

**方式一**
>  alter table t_rpt_city_mapping auto_increment = 1;

**方式二**
> 通过重置表来重置 **自增主键id**
> truncate table table_name

###  2 给用户赋权限
 > grant select on gsdpay.t_urm_minf to bsdrpt;

### 3 生产数据库创建索引
**创建索引**
> CREATE INDEX PAYADM.PK_T_WDC_PAYJNL_INDEX1 ON PAYADM.T_WDC_PAYJNL(WC_JRN_TYP,AC_DT) online parallel 4;<br>
parallel 4 表示4个线程 同时执行 

**创建组合索引**
> CREATE INDEX 索引名 ON 表名 (列名1,列名2)

**删除索引**
> DROP INDEX **索引名**;


### 4 数据库表关系查询

* 查询表属于哪个用户下
    > select * from all_all_tables where OWNER ='PAYADM' <br>
* 查询所有用户下的所有表，可加入筛选条件，如where。。等
    > select * from all_tab_comments where OWNER ='BSDRPT'
* 查询某个用户下的所有表，注意此处用户名要大写
    > select * from all_tab_comments where owner='用户名' ;<br>

* 查询本用户下的表 <br>
    > select * from user_tab_comments;   

* 查询所有用户的信息详细信息<br> 
    > select * from dba_users;    
     

    








