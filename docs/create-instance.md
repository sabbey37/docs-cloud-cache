
# Creating a Pivotal Cloud Cache Service Instance


Run `cf create-service p-cloudcache PLAN-NAME SERVICE-INSTANCE-NAME` to create a service instance. Replace `PLAN-NAME` with the name from the list of available plans. Replace `SERVICE-INSTANCE-NAME` with a name of your choice. Use this name to refer to your service instance with other commands. Service instance names can include alpha-numeric characters, hyphens, and underscores.

<pre class='terminal'>
$ cf create-service p-cloudcache extra-large my-cloudcache
</pre>

Service instances are created asynchronously. Run the `cf services` command to view the current status of the service creation, and of other service instances in the current org and space:

<pre class='terminal'>
$ cf services
Getting services in org my-org / space my-space as user...
OK

name            service        plan    bound apps   last operation
my-cloudcache   p-cloudcache   small                create in progress
</pre>

When completed, the status changes from `create in progress` to `create succeeded`.

## Provide Optional Parameters

You can create a customized service instance by passing optional parameters to `cf create-service` using the `-c` flag. The `-c` flag accepts a valid JSON object containing service-specific configuration parameters, provided either in-line or in a file.

The PCC service broker supports the following parameters:

- `num_servers`: An integer that specifies the number of server instances in the cluster. The minimum value is `4`. The maximum and default values are configured by the operator.
- `new_size_percentage`: An integer that specifies the percentage of the heap to allocate to young generation. This value must be between `5` and `83`. By default, the new size is 2&nbsp;GB or 10% of heap, whichever is smaller.

The following example creates the service with five service instances in the cluster:

<pre class='terminal'>
$ cf create-service p-cloudcache small my-cloudcache -c '{"num_servers": 5}'
</pre>

## <a id="ssc"></a> Enable Session State Caching with the Java Buildpack

When the `session-replication` tag is specified, the Java buildpack downloads all the required resources for session state caching. This feature is available in Java buildpack version 3.19 and higher, up to but not including version 4. It is then available again in version 4.3.

To enable session state caching, do _one_ of the following items:

- Option 1: When creating your service instance name, specify the `session-replication` tag. For example:

    <pre class='terminal'>
     $ cf create-service p-cloudcache small-plan my-service-instance -t session-replication</pre>

- Option 2: Update your service instance, specifying the `session-replication` tag:

    <pre class='terminal'>
    $ cf update-service new-service-instance -t session-replication</pre>

- Option 3: When creating the service, name the service instance name by appending it with the string `-session-replication`,
for example `my-service-instance-session-replication`.

## Enable Session State Caching Using Spring Session

To use
[Spring Session](http://projects.spring.io/spring-session/)
for session state caching for apps with PCC, follow the steps below:

1. Make the following changes to the app:
  * Replace existing Spring Session `@EnableXXXHttpSession` annotation with `@EnableGemFireHttpSession(maxInactiveIntervalInSeconds = N)` where `N` is seconds.
  * Add the `spring-session-data-geode` and `spring-data-geode` dependencies to the build.
  * Add beans to the Spring app config.

    For more information, see the [spring-session-data-gemfire-example](https://github.com/jxblum/spring-session-data-gemfire-example) repository.

2. Create a region named `ClusteredSpringSessions` in gfsh using the `cluster_operator_XXX` credentials:
  ```
  create region --name=ClusteredSpringSessions --type=PARTITION_HEAP_LRU
  ```

## Dev Plans

The Dev Plan is a type of service plan
that is useful for development and testing.
This example creates a Dev Plan service instance:

<pre class='terminal'>
$ cf create-service p-cloudcache dev-plan my-dev-cloudcache
</pre>

The plan provides a single locator and a single server colocated
within a single VM.
Because the VM is recycled when the service instance is updated or upgraded,
all data within the region is lost upon update or upgrade.

When post-deploy scripts are enabled for Ops Manager,
the service instance is created with a single sample region
called `example_partition_region`.
The region is of type `PARTITION_REDUNDANT_HEAP_LRU`,
as described in [Partitioned Region Types for Creating Regions on the Server](region-design.html#partitioned-types).

If `example_partition_region` has **not** been created,
it is probably because post-deploy scripts are not enabled for Ops Manager,
as described in [Configure a Dev Plan](./operator.html#dev-plan).
