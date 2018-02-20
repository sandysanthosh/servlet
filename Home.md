Welcome to the servlet wiki!

servlets:





debug:


Lo4J

 

cookie

session


Locale

Language settings

currency format



file upload

url rewriting


web.xml


Request Dispatcher:


forward

include



deployment description:


<web-app>

<servlet>

<description>

<display-name>

<servlet-class>

</servlet>


<servlet-mapping>

<servlet-name>

<url-patten>

<jsp-file>/Demo.jsp</jsp-file>

</servlet-mapping>

</web-app>


readin url parameter

include file

import file

forward and redirect

jsp implicit object



servelt.class:


PrintWriter out=response.getWriter();

out.println("test");


url parameter:


->doget(HttpServletRequest request,HttpServletResponse response)

{

String args0;

args0 = request.getParameter("get");

out.println(args0);

String arg1 = request.getParameter("get2");

out.println(args1);

}






jsp include:


static content:

<%@ include file="header.jsp" %>

<%@ include file="footer.jsp" %>


used for dynamic content:

<jsp:include page="2.txt"></jsp:include>


import file in jsp:


only data type could be imported:


<%@ page import="java.util.Date" %>

<%@ page import="imports.Demo" %>


<%= new Date()%>

<%= new Demo().test() %>


generic method:


forward and redirect:


forward in jsp:


<jsp:forward page="forward.jsp"></jsp:forward>


forward in servlet:


<%

request.getRequestDispatcher("forward.jsp").forward(request,response);

%>


<%

respose.sendRedirect("redirect.jsp");

%>




controller.java:


String page=null;


String param=request.getParameter("page");

if(param.equals("login")){

   page="/login.jsp/";}

else if(param.equals("signup")){

   page="signup.jsp";}

else if(param.equals("about")){

   page="about.jsp";}

else{

   page="/notFound.jsp";

}


getServletContext().getRequestDispatcher(page).forward(request,response);


}


forms:


gmail

facebook

udemy

travels search(makemytrip)


interact with web-server:


form-> request  ->web app

       response 


methods:

get

post


from under jsp:


html

head 


form using servlets:


In JSP:


<body>

<form acction="so2Lo1_Forms/controller">

Email:<input type="text" name="email">

password:<input type="text" name="password">

<input type="submit" value="submit">

</body>


IN servlets:


goGet(HttpServletRequest request,HttpServletResponse response) throw

{

string email=request.getParameter("email");

string password=request.getParameter("password");

PrintWriter out=response.getWriter();

if(eamil.equals("chand") and password.equals("123456"))

{

out.println("Welcome!");

}

else

{

out.printlnt("Login Failed");

}


html5 form validations:


->required

->read only

->email

->disabled

->maxlength->maximum character

->min

->max

->pattern

->list



form validation using javascript:


<form action="" method="post" name="sample" onsubmit="return validate()">


</form>




<Script>


function validate()

{

var leng=document.forms["sample"]["password"].length;

if(leng < 8 )

    alert("password is less");

}

else

{

return true;

}


</script>




session under jsp:


form in jsp:

sevlets:


doGet()

{

HttpSession session=request.getSession();

session.setAttribute("sessionName",request.getParameter("name"));

PrintWriter out=response.getWriter();

}


session in jsp:


<%


String name=(String)session.getAttribute("sessionName");


if(name =="" || name ==null){

name="User";

}


%>



<%=name %>



java:


j2se->core java + jdbc

j2ee->jsp + servlets

j2m2->



DELETE  a data from list:


<li>{to.list} & ndsp; & nbsp; <a href="/delete-todo.do">Delete</a></li>


delete-TodoServlet.do:


TodoService todo = new TodoService();


doGet(request, response){

todo.deleteTodo(new Todo(request.getParameter("todo"));

response.sendRedirect("delete.todo");

}

doPost(request, response)



TodoService.java:


List<Todo> todos=new ArrayList<Todo>();

static{

todos.add(new Todo("learn web appa"));

todos.add(new Todo("learn Spring MVC"));

todos.add(new Todo("learn Spring Rest"));

}


public void addTodo(Todo todo)

{

todo.add(todo);

}


public void DeleteTodo(Todo todo)

{

todo.remove(todo);

}



->generate equals and hashcode




bootstrap & jquery add:


add in pom.xml maven:


<dependency>

<groupid>org.webjars<groupid>

<artifacts>bootstrap<artifacts>

<version>3.3.5<version>

</depenedency>


<dependency>

<groupid>org.webjars<groupid>

<artifacts>jquery<artifacts>

<version>3.3.5<version>

</depenedency>


bootstrap:


navigation

div container

header

footer



<footer>

position:absolute;

bottom:0;

width:100%;

height:60px;

background-color: #f5f5f;

}



get paramete using jsp:



@WebServlet( urlPatterns = "/login.do")

doGet(R, R){

string name=request.getParameter("name");

request.setAttribute("name",name);\

request.getRequestDispatcher("/WEB-INF/VIEWS/LOGIN.JSP").forward(R,R);

}


name attribute show in jsp:


get if not secured:


->all the routers can able to see the passwords



form method="post":

-> in servlet it should have post method


method post in serlvet:


method="post"


servlet->doPost()




Bean:


use Bean Action Elements:

<jsp:useBean id="u" class="org.sssit.User"></jsp:useBean>  
<jsp:setProperty property="*" name="u"/>  
