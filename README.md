# Logback Throttling appender

An appender that can be throttled ;-)

## Features

 todo: describe features

## Requirements

- Java 17
- Logback 1.2.9


## Examples

Simple configuration:

```xml
<configuration>

    <appender name="listAppender" class="ch.qos.logback.core.read.ListAppender"/>

    <appender name="Throttle" class="be.dnsbelgium.logback.ThrottlingAppender">
        <bufferSize>10</bufferSize>
        <maxMessagesToEmitAfterStartUp>6</maxMessagesToEmitAfterStartUp>
        <maxMessagesToEmitAfterWakeUp>3</maxMessagesToEmitAfterWakeUp>
        <appender-ref ref="listAppender" />
    </appender>

    <root level="debug">
        <appender-ref ref="Throttle" />
    </root>

</configuration>
```

For more examples, see [./src/test/resources/](./src/test/resources/)
