# congomall-gateway	外部网关	http://localhost:8003

with only @EnableDiscoveryClient
```
@EnableDiscoveryClient
@SpringBootApplication
public class GatewayApplication {
    
    public static void main(String[] args) {
        SpringApplication.run(GatewayApplication.class, args);
    }
}

```

DiscoveryClient implementations include Spring Cloud Netflix Eureka, Spring Cloud Consul Discovery, and Spring Cloud Zookeeper Discovery


Commons now provides a ServiceRegistry interface which provides methods like register(Registration) and deregister(Registration) which allow you to provide custom registered services. Registration is a marker interface.

https://cloud.spring.io/spring-cloud-commons/2.0.x/multi/multi__spring_cloud_commons_common_abstractions.html#_serviceregistry


Actuator Endpoint

