http://www.coderanch.com/t/615435/JDBC/databases/JDBC-Connect-Table-View-CATEGORY


1.go to WEB-INF/glassfish-web.xml 
2. add resource-ref 
<resource-ref> 
<res-ref-name>jdbc/affablebean</res-ref-name> 
<jndi-name>jdbc/affablebean</jndi-name> 
</resource-ref> 


http://stackoverflow.com/questions/27148401/cdi-imports-cannot-be-resolved-in-eclipse

Do you happen to use the GlassFish Tools plugin for Eclipse? I found that the GlassFish System Libraries classpath container, which is created implicitly by that plugin and which is added to all projects that specify a GlassFish server as their runtime, misses cdi-api.jar. This is where the javax.enterprise.context.* package is located (and many others).

So I could fix this by adding cdi-api.jar as an External Jar to the build path. After that, you may get a warning like Classpath entry [...]/cdi-api.jar will not be exported or published. Runtime ClassNotFoundExceptions may result., which can be eliminated by using the Quick Fix to Exclude the associated raw classpath entry from the set of potential publish/export dependencies. That JAR file is already contained in the modules folder of GlassFish, obviously.

Maybe this problem only occurs with the GlassFish Web Profile, at least that's what I use.

add this in the persistence.xml --> <property name="eclipselink.persistencexml" value="../../META-INF/persistence.xml"/>