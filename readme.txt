作者: hzboy192@192.com

版本：1.0

使用技术说明：

1.使用struts2+spring3+hibernate3整合实现用户CRUD功能。

2.使用多种配置方式 

	A.将hibernate从外部导入,使用MySQL作为数据库。
	
	B.将hibernate实体映射集成到spring配置文件中。
	
3.使用传统的配置文件集成框架。

4.注意以下问题：
	
	A.当使用spring管理struts2的 action时要注意需在struts2的action配置文件中添加
	  <constant name="struts.objectFactory" value="spring" />，并且需要
	     将struts2-spring-plugin-2.2.1.jar添加到classpath中去。
    
    B.Demo默认Hibernate的DataSource、HibernateProperties、MappingResources
                 信息配置到applicationContext.xml文件中。如果使用Hibernate.cfg.xml配置这些
                 信息，需要在applicationContext.xml文件中将configLocation这个属性去掉注释，
                 并将其他的property注释或删除。
                 
    C.如要将Struts2的默认配置文件struts.xml文件重命名或移动到WEB-INF到下去，需要在
    web.xml的配置struts2过滤器中添加如下代码：
    <init-param>
    	<description>我的struts配置文件放在WEB-INF根目录下，文件名为action.xml</description>
  		<param-name>config</param-name>
  		<param-value>struts-default.xml,struts-plugin.xml,../action.xml</param-value>
  	</init-param>
  	
  	D.如果需要将spring的配置文件移动到其他文件夹或修改名字，需要在web.xml中添加如下代码：
  	 <context-param>
  	 	<description>我的spring配置文件放在WEB-INF根目录下，文件名为springconfig.xml</description>
  		<param-name>contextConfigLoaction</param-name>
  		<param-value>/WEB-INF/springconfig.xml</param-value>
  	</context-param>  
  	
  	
  	
  