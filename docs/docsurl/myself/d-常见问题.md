

### npm命令

*  npm -v 查看版本

* 错误解决
    ```
    npm cache clean --force  (后者执行报错就使用这个命令执行)   或者 npm cache clean 这个命令有时会提示错误信息：D:\2019work\tool\nodejs\node_modules\npm>npm cache clean
    npm ERR! As of npm@5, the npm cache self-heals from corruption issues and data extracted from the cache is guaranteed to be valid. If you want to make sure everything is consistent, use 'npm cache verify' instead. On the other hand, if you're debugging an issue with the installer, you can use `npm install --cache /tmp/empty-cache` to use a temporary cache instead of nuking the actual one.
    npm ERR!
    npm ERR! If you're sure you want to delete the entire cache, rerun this command with --force.
    npm ERR! A complete log of this run can be found in:
    npm ERR!     C:\Users\zhao\AppData\Roaming\npm-cache\_logs\2019-08-28T09_56_07_694Z-debug.log
        
    执行 npm install 时 ，出现 解析错误的信息， 
    解决：
    执行npm -g i npm@4，降低npm的版本，然后重新npm install即可
    之后执行npm start
    ```

### git 

     
    * 错误提示 使用Git提示错误信息： error: you need to resolve your current index  first <br>
    需要执行 -> git reset --merge
    
### sql处理

* 查询结果的数据类型不一致

> select to_char(sysdate-1,'yyyyMMdd') from dual  --返回varchar类型 <br>
  select to_char(sysdate,'yyyyMMdd')-1 from dual --返回number类型 <br>
  可以使用如下命令解决：<br>
  1、 使用to_char 转为char类型比较
  select * from  GSDPAY.T_PAY_JNL c where c.post_ac_dt >=  ( to_char(sysdate-1,'yyyyMMdd')  ) and c.TX_DT <= ( to_char(sysdate,'yyyyMMdd')-1  );<br>
  2、 to_date(c.post_ac_dt,'yyyyMMdd') > TRUNC(SYSDATE) 

* 金额转字符串格式并，对金额精度(或小数点前的0)做处理
> Select to_char(sum(ord_amt),'fm9999999999999990.00')as ord_amt  from tab1


 ### excel 
* POI生成excel遇到的问题
    ```
    java.lang.IllegalStateException: The maximum number of cell styles was exceeded. You can define up to 4000 styles in a .xls workbook
    POI导出execl时在本地测试没有异常，在发布到正式环境后报上面的异常，原因是在for循环里创建了 HSSFCellStyle style = wwb.createCellStyle()对象，所有当导出数据很多时就会报上面的异常 

    解决办法：将HSSFCellStyle style = wwb.createCellStyle();放在循环外面就可以了
    ```




