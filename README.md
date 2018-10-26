# JavaEE-MVC-Starter

1. JAVA EE is used in this project to create MVC starter project.
2. pom.xml has only 1 dependency and it won't be part of the war since Target server Tomcat have the EE library.
        <dependency>
            <groupId>javax</groupId>
            <artifactId>javaee-web-api</artifactId>
            <version>6.0</version>
            <scope>provided</scope>
        </dependency>
3. Here is the LoginServlet config. Web.xml doesn't have any servlet.
      @WebServlet(urlPatterns = "/login.do")
      public class LoginServlet extends HttpServlet {
4. pom.xml has tomcat plugin. this will get tomcat7 server from repository and deploy the war into it, to make it happen,
    Right click on the project -> Run As -> Maven Build... ->  Goals -> tomcat7:run -> http://localhost:8080/
            <plugin>
                <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat7-maven-plugin</artifactId>
                <version>2.2</version>
                <configuration>
                    <path>/</path>
                    <contextReloadable>true</contextReloadable>
                </configuration>
            </plugin>
 
