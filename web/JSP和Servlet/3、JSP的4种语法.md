### JSP开发步骤：

    1.编写一个静态HTML页面
    2.用合适的语法向静态HTML页面中“镶嵌”4种基本语法的一种或多种，这样即可为静态HTML页面增加动态内容

####1、 JSP注释

JSP注释格式：

`<%--注释内容--%>`

HTML注释格式：

`<!--HTML注释-->`

注：

    HTML的注释可以通过源代码查看，但JSP的注释无法通过源代码看到。这说明JSP注释不会发送到客户端


#### 2、JSP声明

JSP声明用于声明变量和方法。JSP声明将会转换成对应Servlet的成员变量或成员方法。

JSP声明的语法格式：

`<%! 声明部分 %>`

例：

	<%@ page contentType="text/html; charset=GBK" language="java" errorPage="" %>
	<html>
	<head>
	    <title>欢迎</title>
	</head>
	<body>
	<%! 
	public int count;
	public String info(){
	    return "hello";
	}
	%>
	<%
	out.println(count++);
	%>
	<br/>
	<%
	out.println(info());
	%>
	</body>
	</html>

浏览器每刷新一次，count的值加1

注：JSP声明语法定义的变量和方法对应于Servlet类的成员变量和方法，所以JSP声明部分定义的变量和方法可以使用private、public 等访问修饰符，也可以使用static修饰，将其变成类属性和类方法

JSP编译的Servlet类是个单例类，所以每个Servlet在容器中只有一个实例；JSP中声明的变量是成员变量，成员变量只有在创建实例时初始化，该变量的值将一直保存，直到实例销毁。

####3、JSP输出表达式

输出表达式语法：

`<%= 表达式 %>`

**注：**

    1）输出表达式将转换成Servlet里的输出语句
    2）输出表达式语法后不能有分号


####4、JSP小脚本

通常所有可执行性Java代码都可通过jsp小脚本嵌入HTML页面

	<%@ page contentType="text/html; charset=GBK" language="java" errorPage="" %>
	<html>
	<head>
	    <title>欢迎</title>
	</head>
	<body>
	<table>
	<%
	for(int i = 0; i < 10; i++){
	%>
	    <tr>
	        <td>循环值：</td>
	        <td><%= i %></td>
	    </tr>
	<%
	}
	%>
	</table>
	</body>
	</html>

注：JSP小脚本中也可声明变量，但在JSP小脚本部分声明的变量是局部变量，不能使用private、public等访问控制符修饰，也不可用static修饰

可利用小脚本连接数据库，数据库的驱动放在tomcat下的lib路径下，或者复制到WEB-INF/lib下