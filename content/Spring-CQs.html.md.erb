---
title: Creating Continuous Queries Using Spring Data GemFire
---
<a id="CQs-spring-data-gemfire"></a>

To create continuous queries with the Spring Data GemFire library, you must have the following:

* Spring Data GemFire v2.0.1 release
* Spring Boot v2.0.0+

To create continuous queries, do the following  items:

- Specify attributes `subscriptionEnabled` and `readyForEvents` for
the `ClientCacheApplication` annotation.
Apply this annotation to the Spring Boot client application class: 

    ```java
    @ClientCacheApplication(name = "GemFireSpringApplication", readyForEvents = true,
      subscriptionEnabled = true)
    ```
The annotation for a durable event queue for continuous queries also sets the
`durableClientId` and `keepAlive` attributes. For example:

    ```java
    @ClientCacheApplication(name = "GemFireSpringApplication",
      durableClientId = "durable-client-id", keepAlive = true,
      readyForEvents = true, subscriptionEnabled = true)
    ```
-  Annotate the method that handles the events to specify the query.
To make the event queue durable across server failures and restarts,
include the `durable = true` attribute in the annotation,
as is done in the example:

    ``` java
    @Component
    public class ContinuousQuery {

        @ContinuousQuery(name = "yourQuery",
           query = "SELECT * FROM /yourRegion WHERE someAttribute == true",
           durable = true)
        public void handleChanges(CqEvent event) {
          //PERFORM SOME ACTION
        }
    }
    ```
    The class that contains the method with the @ContinuousQuery annotation must have the @Component annotation, such that the continuous query is wired up correctly for the server.
    

For more information, see the [Spring Data GemFire documentation](https://docs.spring.io/spring-data/gemfire/docs/current/reference/html/).
