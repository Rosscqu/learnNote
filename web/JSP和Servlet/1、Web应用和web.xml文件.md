###构建web应用

web应用目录组成：

    webDemo：Web应用的名称
        ——WEB-INF：
			——classes：保存Web应用所需要的Java类文件，保存*.class文件
			——lib：也是保存Web应用所需要的Java类文件，保存JAR文件
			——web.xml：配置描述符。在Servlet2.5之前，每个Java web应用都必须包含一个web.xml文件，且必须在WEB-INF路径下
    	 ——<a.jsp> 存放任意多格JSP页面

web.xml配置内容：

	配置JSP
	配置和管理Servlet
	配置和管理Listener
	配置和管理Filter
	配置标签库
	配置JSP属性
	配置和管理JAAS授权认证
	配置和管理资源引用
	Web应用首页
	metadata-complete：该属性接受true和false
