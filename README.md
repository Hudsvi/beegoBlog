# Beego Blog  

通过本博客，你可以了解到：
    
    orm的高级用法；go模板（不使用其他js插件）实现分页功能；mvc模式下视图和模型的高内聚低耦合写法；  

    IP访问：[180.76.160.86/blog](http://180.76.160.86/blog)  

    域名访问：[hudsvi.com/blog](http://hudsvi.com/blog) 或[hudsvi.cn/blog](http://hudsvi.cn/blog) ，域名无法访问说明域名正在备案中，请先使用IP访问。  

## **注意：**  
1.beegoBlog/src/github.com/... 包下的beego框架和bee工具请自行执行下面的命令引入。  
    
    （1）配置GOPATH：`  go export GOPATH='pwd' `（cd 到 beegoBlog包下执行）。  

    （2）远程获取并编译beego： ` go get github.com/astaxie/beego `  
    
    （3）远程获取并编译bee：` go get github.com/beego/bee `  

2.无需自己创建表，只需创建自己的数据库即可，ORM数据库建表和CURD操作。修改下面两处,可自定义数据库表。  

（1）conf/app.conf文件  
  
    该文件是配置文件，不多累赘。你只需要将dbuser、dbpass、dbhost等属性改为你自己的登陆用户名和数据库名即可。  
  
（2）model/models.go  
 
    该文件中的一系列struct决定了表的结构，包括表名、依赖关系和约束等。字段名最好用驼峰命名，orm会自动帮你转“_”），博客中有个Created字段，orm type为date，对应类型应该是time.Time，而我为了方便显示，created定义的类型是string,生成表时，created字段变为varchar，所以你得手动修改。  
	
另外想了解更多，请参阅[beego谢孟军的官网](https://beego.me/docs/intro/)  
	
3.当前版本是发布版，所以runmode=prod,并且日志控制级别设置为2（事先定义1为dev,2为prod），如果想变更这些参数，可分别在conf/app.conf和utils/log/log.go中进行调整。  

## 关于xhEditor编辑器
本博客网站轻微地修改了xhEditor：  

1.关闭强制p标签  

2.添加插入代码插件，pre标签的样式已经在css文件中定义，简化了代码的展示。

改动后：  

开启强制<p>标签。
