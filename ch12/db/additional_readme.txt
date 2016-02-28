http://www.coderanch.com/t/615435/JDBC/databases/JDBC-Connect-Table-View-CATEGORY


1.go to WEB-INF/glassfish-web.xml 
2. add resource-ref 
<resource-ref> 
<res-ref-name>jdbc/affablebean</res-ref-name> 
<jndi-name>jdbc/affablebean</jndi-name> 
</resource-ref> 