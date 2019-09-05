### failsafe-actuator
---
https://github.com/zalando/failsafe-actuator

```java
// src/test/java/org/zalando/actuate/failsafe/EmptyCircuitBreakersEndpointTest.java

@RunWith(SpringRunner.class)
@SpringBootTest(classes = NoCircuitBreakerApplication.class, webEnvironment = RANDOM_PORT)
public class EmptyCircuitBreakerEndpointTest {
  
  @Autowired
  private TestRestTemplate http;
  
  @Test
  public void shouldReadAll() {
    final Map<String, CircuitBreakerView> breakers = readAll().getCircuitBreakers();
    
    assertEquals(0, breakers.size());
  }
  
  private Container readAll() {
    return http.exchange("/actuator/circuit-breakers", GET, EMPTY, Container.class).getBody();
  }
}
```

```
```

```
```


