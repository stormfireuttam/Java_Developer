

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