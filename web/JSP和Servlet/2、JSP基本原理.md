### JSP基本原理


本质：

    JSP的本质是Servlet（特殊的JAVA类），当用户向指定的Servlet发送请求时，Servlet利用输出流动态生成HTML页面，包括每一个静态的HTML标签和所有在HTML页面中出现的内容。

JSP页面的内容组成：

    静态部分：标准的HTML标签、静态的页面内容，这些内容与静态HTML页面相同
    动态部分：受Java程序控制的内容，这些内容由Java脚本动态生成

注：

    JSP的本质时Servlet的理解：每个JSP页面就是一个Servlet实例——JSP页面由系统编译成Servlet，Servlet在负责响应用户请求。也就是说，JSP其实时Servlet的简化，使用JSP时，其实还是使用Servlet，因为Web应用中的每个JSP页面都会由Servlet容器生成对应的Servlet。对于Tomcat而言，JSP页面生成的Servlet放在work路径对应的Web应用下。

Servlet类源码组成：

    init():初始化JSP/Servlet的方法
    destroy():销毁JSP/Servlet的方法
    service():对用户请求生成响应的方法

JSP页面工作原理：

    JSP页面必须在JSP服务器内部运行
    JSP文件必须生成Servlet才能执行
    每个JSP页面的第一个访问者速度会有点慢，因为必须等待JSP编译成Servlet
    JSP页面的访问者无需安装任何客户端，甚至不需要可以运行Java的运行环境，因为JSP页面输送到客户端的是标准的HTML