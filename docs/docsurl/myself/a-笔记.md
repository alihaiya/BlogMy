
## 随记

### 支付跳码

```java
线下商户交易，可能会存在跳码的问题；而线上则不存在。 
跳码有两种情况，一种是商户类别跳码，一种是交易地点跳码。 
线下POS消费需要通过银联进行交易。银联针对不同类别的商户，制定了不同的交易费率，标准类费率为0.6%，优惠类费率为0.38%，公益类费率为0%。 
用户消费商户的类型，和实际交易通道的商户类型不一致，就称之为跳码，比如用户消费类型为标准类，而实际支付通道的消费类型为优惠类或者公益类，就是跳码。 
商户类别跳码的情况严重影响了发卡行的收益，因此，对于持卡人来说，经常使用跳码POS刷卡，会被银行列入风控名单中。 
交易地点跳码，就是消费商户的地点和交易地点不一致，会被银行认为是套现行为，持卡人同样有可能会被列入银行的风控名单中。 
而线上商户交易，其本身就是互联网商户，不存在交易地点跳码的情况；另外，虽然线上交易渠道也有费率高低区分，但是却不存在跳码的情况，因为线上交易通道的费率，一般都要比线下低。 

```
 

### String数组使用场景
```java
@Test
publicvoidtest1(){
    String[]totalData=newString[]{};
    StringBuildersb=newStringBuilder();
    sb.append("总计").append("/").append("/").append("/").append("/").append("/");
    sb.append("01").append("/").append("02").append("/").append("03").append("/")
    .append("04").append("/").append("05");
    StringsbStr=sb.toString();
    logger.info("sumdatais:"+sbStr);
    totalData=sbStr.split("/");
    for(inti=0;i<totalData.length;i++){
    System.out.println(totalData[i]);
    }
}

``` 
 
### Excel工具类

> 使用创建转换器衬例

### Maven 


#### 常用命令
* 打包命令
>  Mvn claen package -DskipTest=true -Ppro    说明：  mvn命令行打包,-P 后指定使用环境配置
* 设置POM.xml 
```
在标签 profile  下配置 
<activation>
<activeByDefault>true</activeByDefault>
</acivation>
```
    
 ### git 一般操作
```
第一种方法：（简单易懂）

1、git add .（后面有一个点，意思是将你本地所有修改了的文件添加到暂存区）
2、git commit -m""(引号里面是你的介绍，就是你的这次的提交是什么内容，便于你以后查看，这个是将索引的当前内容与描述更改的用户和日志消息一起存储在新的提交中)
3、git pull origin master 这是下拉代码，将远程最新的代码先跟你本地的代码合并一下，如果确定远程没有更新，可以不用这个，最好是每次都执行以下，完成之后打开代码查看有没有冲突，并解决，如果有冲突解决完成以后再次执行1跟2的操作
4、git push origin master 将代码推至远程就可以了
```
  






    
