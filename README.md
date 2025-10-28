# lab-4-eureka-server-danim

The Spring Cloud Eureka is a feature that allows to register different services (clients) in a Eureka server to discover them to be accessible from other clients. 
This project acts as an **Spring Cloud Eureka server project**, that registers and discovers several service clients.
In this example, the client repos **lab-4-subject, lab-4-verb, lab-4-article, lab-4-adjective** and **lab-4-noun** are registered in the Eureka server to be discovered and accessible.
Then an additional client, **lab-4-sentence**, can use all of them to mount a complete sentence.

# Starting the application

Steps to start the Eureka infrastructure:
- Start the Java class annotated by @SpringBootApplication and check it's started correctly in http://localhost:8010
- Start the different client repos **lab-4-subject, lab-4-verb, lab-4-article, lab-4-adjective** and **lab-4-noun**. They will be started in aleatory ports in localhost.
- Start the client repo **lab-4-sentence**. Check that the sentence is shown in the URL http://localhost:8020/sentence

# Dependencies

Eureka Server

# Tips

- The project starting class is annotated with **@SpringBootApplication** and also with @EnableEurekaServer to indicate that acts as an Eureka Server
- If the client services that are registered in this Eureka Server also use Spring Cloud Config feature to load configuration from the **spring-cloud-server-config-danim** Git reposirtory, then the **application.yml** config file shoud include the following configuration to avoid connecting to anon-existing Eureka config server:

```yaml
eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
```

