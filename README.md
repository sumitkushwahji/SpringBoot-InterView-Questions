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

```


application-prod.yml (Production Configuration):
```java
spring:
  profiles: prod
  jpa:
    show-sql: false # Disable SQL logging for production
  # Add other production-specific settings

upload:
  dir: src/prod-files # Define the directory for storing uploaded files in production
```

In this configuration:

The application-dev.yml file contains properties specific to the development environment. In this case, we enable SQL logging and specify a different directory for storing uploaded files.

The application-prod.yml file contains properties specific to the production environment. We disable SQL logging and specify a different directory for storing uploaded files.

To activate a specific profile (either 'dev' or 'prod'), set the spring.profiles.active property in your main application.yml. For example:

application.yml:

```java
spring:
  profiles:
    active: dev # or prod to activate the production profile
```
Setting spring.profiles.active to 'dev' will load the configuration from application-dev.yml, and setting it to 'prod' will load the configuration from application-prod.yml. You can easily switch between profiles by changing the value of spring.profiles.active in the main application.yml file.
