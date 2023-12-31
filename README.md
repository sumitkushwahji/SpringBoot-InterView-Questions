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

## Spring Boot Actuator

Spring Boot Actuator is a set of production-ready features that can be added to your Spring Boot application to monitor and manage it. Actuators provide various built-in endpoints that expose useful information about your application, including health, metrics, environment properties, application properties, and more. These endpoints are valuable for monitoring and managing your application in a production environment.

To add Spring Boot Actuator to your application, you need to include the spring-boot-starter-actuator dependency in your project. For example, if you're using Maven, you can add the following dependency to your pom.xml:
```java
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```
After adding the dependency, you can configure Actuator endpoints and their properties in your application.properties or application.yml file. For example, to enable all default endpoints, you can add the following configuration:

```java

management.endpoints.web.exposure.include=*
```
Spring Boot Actuator is a powerful tool for monitoring, managing, and troubleshooting your Spring Boot application in a production environment. However, you should be cautious when exposing sensitive information or enabling certain endpoints in a production environment to ensure security and privacy.


## Stream API
The Stream API in Java is a powerful and expressive way to process sequences of data, such as collections (e.g., lists, sets, and maps), arrays, or I/O channels, in a functional style. Introduced in Java 8, it provides a clean and concise way to perform common data manipulation operations, like filtering, mapping, reducing, and transforming data, while making your code more readable and expressive.

Key features of the Java Stream API:

### Functional Programming: 
The Stream API encourages a functional programming approach, where you define what you want to do with the data rather than how to do it. This leads to cleaner and more concise code.

### Lazy Evaluation:
Streams use lazy evaluation, meaning operations are performed only when necessary. This can lead to improved performance for large datasets.

### Chaining:
You can chain multiple operations together, creating a pipeline of transformations and operations on the data.

### Immutable Data: 
Streams do not modify the underlying data. Instead, they create new streams with the transformed data, leaving the original data intact.

### Parallel Processing:
Java Streams can easily be parallelized to take advantage of multi-core processors for parallel execution of operations.

Here are some common operations you can perform using the Java Stream API:

### Filtering: 
You can filter elements based on a specified condition.

```
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
List<Integer> evenNumbers = numbers.stream()
    .filter(n -> n % 2 == 0)
    .collect(Collectors.toList()); // [2, 4]
```
### Mapping:
You can transform elements using a given function.

```
List<String> names = Arrays.asList("John", "Alice", "Bob");
List<Integer> nameLengths = names.stream()
    .map(String::length)
    .collect(Collectors.toList()); // [4, 5, 3]
```

### Reducing:
You can combine elements into a single value (e.g., sum, product, or finding the maximum).

```
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
int sum = numbers.stream()
    .reduce(0, Integer::sum); // 15
```

### Sorting: 
You can sort elements in ascending or descending order.

```
List<Integer> numbers = Arrays.asList(5, 3, 1, 4, 2);
List<Integer> sortedNumbers = numbers.stream()
    .sorted()
    .collect(Collectors.toList()); // [1, 2, 3, 4, 5]
```

### Grouping and Aggregating: 
You can group elements by a key and perform aggregate operations.

```
List<Person> people = ... // List of Person objects
Map<Gender, List<Person>> peopleByGender = people.stream()
    .collect(Collectors.groupingBy(Person::getGender));
```
### Parallel Processing: 
You can leverage parallel streams to process data in parallel.

```
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
int sum = numbers.parallelStream()
    .reduce(0, Integer::sum); // Parallel reduction
```
The Stream API in Java is a powerful tool for working with data in a functional and expressive way. It simplifies the code and makes it easier to write, read, and maintain data processing operations. Streams are widely used in Java applications for various data manipulation tasks.






