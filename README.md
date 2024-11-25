# Circuit Breaker Example

This is an example of how to use **Resilience4j Circuit Breaker** 😃

## Concepts used in this example

- This example is based on the [Spring Cloud Circuit Breaker Guide](https://spring.io/guides/gs/cloud-circuit-breaker).
- The project consists of two applications: a client application (**Reading**) and a server application (**Bookstore**).
  - The **Reading** application runs on port **8080**.
  - The **Bookstore** application runs on port **8090**.
- The **Reading** application makes a `GET /recommended` call to the **Bookstore** endpoint.
- The **Reading** application uses the **ReactiveCircuitBreaker**, which is auto-configured through the "starter" dependency.
- If the **Bookstore** application returns an error, the **ReactiveCircuitBreaker** uses a fallback function to handle the error gracefully:
  ```java
  return Mono.just("Cloud Native Java (O'Reilly)");
  ```
