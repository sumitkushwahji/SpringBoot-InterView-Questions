# SpringBoot-InterView-Questions

## Profiling in Spring Boot
Profiling in Spring Boot is a technique that allows you to manage application-specific configurations for different environments or scenarios, such as development, testing, and production. It's a powerful feature that helps you customize your application's behavior and settings based on the active profile. Spring Boot makes it easy to work with profiles, and you can create and use profiles to tailor your application to various deployment and runtime environments.

Here are the key aspects of profiling in Spring Boot:

Profile Definitions:

Active Profiles: Active profiles determine which set of configuration properties and beans are used in your application. You can set the active profile using the spring.profiles.active property. This property can be configured in various ways, including in application.properties or application.yml, through command-line arguments, environment variables, and system properties.
Default Profiles: Default profiles are profiles that are automatically active when no other profiles are explicitly set as active. You can set default profiles using the spring.profiles.default property.
Profile-Specific Configuration:

You can create profile-specific configuration files using the naming convention application-{profile}.properties or application-{profile}.yml. For example, application-dev.properties for the development profile and application-prod.yml for the production profile.
Profile-specific configuration files allow you to override properties and define profile-specific settings.
Property Sources:

Spring Boot combines properties from various sources. The order of precedence for property sources, from highest to lowest precedence, is as follows:
a. Profile-specific properties (e.g., application-dev.properties).
b. Regular application.properties or application.yml.
c. Command-line arguments.
d. Environment variables.
e. System properties.
