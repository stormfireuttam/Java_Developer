

# Adding a simple controller

Create a controller package under com.example.helloworld.
Create a Java class named HelloController. And make the content like below.

        @Controller
        public class HelloController {
            private Map<String, Object> result = new HashMap<>();

              @RequestMapping("/hello")
              @ResponseBody
              public Map<String, Object> hello() {
                 result.put("name", "Stephen");
                 result.put("city", "San Jose");
                 return result;
              }
          }

If you see any red bulb, click that and select import. Will solve the import issue. Notice that IntelliJ will automatically add the dependency to your pom.xml file. For this example, the spring-boot-web will be added to your dependency list.

    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-web</artifactId>
    </dependency>

Now you can run command below in your IntelliJ Terminal:

**mvn spring-boot:run** 

Once you see something like “Completed initialization in xxx ms”. Open a browser, and goto
http://localhost:8080/hello
You should see something like “{"city":"San Jose","name":"Stephen"}



# Difference between Simple Controller and a Rest Controller

@RestController is a specialized version of controller, which includes @Controller and @ResponseBody. In this example, we are going to use it to update our existing Controller class we created previously. 

Spring’s annotation-based mvc framework simplifies the process of creating restful web services. the key difference between a traditional spring mvc controller and the restful web service controller is the way the http response body is created. while the traditional mvc controller relies on the view technology, the restful web service controller simply returns the object and the object data is written directly to the http response as json/xml.

