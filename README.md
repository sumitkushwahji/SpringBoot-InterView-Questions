# SpringBoot-InterView-Questions

## Profiling in Spring Boot
Profiling in Spring Boot is a technique that allows you to manage application-specific configurations for different environments or scenarios, such as development, testing, and production. It's a powerful feature that helps you customize your application's behavior and settings based on the active profile. Spring Boot makes it easy to work with profiles, and you can create and use profiles to tailor your application to various deployment and runtime environments.

Here are the key aspects of profiling in Spring Boot:

application-dev.yml (Development Configuration):
```java
spring:
  profiles: dev
  jpa:
    show-sql: true # Enable SQL logging for dev
  # Add other dev-specific settings

upload:
  dir: src/dev-files # Define the directory for storing uploaded files in dev

