
# Monitor Your Java Apps with Spring Boot Actuator

This repository shows you how to use the Spring Boot [Actuator](https://spring.io/guides/gs/actuator-service/) project to monitor your app.

It also extends the base functionality to be able to monitor all the HTTP traffic during an [OpenID Connect](https://openid.net/connect/) authentication flow.

The blog post that references this repository can be found on the [Okta Developer Blog](https://developer.okta.com/blog/2019/07/17/monitoring-with-actuator).

**Prerequisites:** [Java 8](https://adoptopenjdk.net/).

> [Okta](https://developer.okta.com/) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's intuitive API and expert support make it easy for developers to authenticate, manage, and secure users and roles in any application.

* [Getting Started](#getting-started)
* [Links](#links)
* [Help](#help)
* [License](#license)

## Getting Started

To install this example, run the following commands:

```bash
git clone https://github.com/oktadeveloper/okta-spring-boot-custom-actuator-example.git
cd okta-spring-boot-custom-actuator-example
```

### Create an Application in Okta

Log in to your Okta Developer account (or [sign up](https://developer.okta.com/signup/) if you don’t have an account).

1. From the **Applications** page, choose **Add Application**.
2. On the Create New Application page, select **Web**.
3. Note the **Client ID** and **Client Secret** values.

### Build your app and start the server

```
OKTA_OAUTH2_REDIRECTURI=/authorization-code/callback \
OKTA_OAUTH2_ISSUER=https://{yourOktaDomain}/oauth2 \
OKTA_OAUTH2_CLIENT_ID=<client id> \
OKTA_OAUTH2_CLIENT_SECRET=<client secret> \
./mvnw spring-boot:run
```

Go to [/hello/greeting](http://localhost:8080/hello/greeting "demo application").

### View the HTTP Trace

After the login, go to [/actuator/httptrace](http://localhost:8080/actuator/httptrace "actuator link").

## Links

This example uses the following open source libraries:

* [**Java Microservices with Spring Boot and Spring Cloud**](https://developer.okta.com/blog/2019/05/22/java-microservices-spring-boot-spring-cloud_)
* [**Spring Boot Actuator Endpoints**](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-endpoints.html)
* [**Implementing Custom Endpoints**](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-endpoints.html#production-ready-endpoints-custom)
* [**Okta Authentication Quickstart Guides Java Spring**](https://developer.okta.com/quickstart/#/okta-sign-in-page/java/spring)

## Help

Please post any questions as comments on the [blog post](https://developer.okta.com/blog/2019/07/17/monitoring-with-actuator), or on the [Okta Developer Forums](https://devforum.okta.com/).

## License

Apache 2.0, see [LICENSE](LICENSE).

