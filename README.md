# Log4j Log4j 2 - Remote Code Execution (RCE)
Apache Log4j 2 is an upgrade to Log4j that provides significant improvements over its predecessor, Log4j 1.x, and provides many of the improvements available in Logback while fixing some inherent problems in Logback's architecture.

# Usage 
Users should refer to Maven, Ivy, Gradle, and SBT Artifacts on the Log4j web site for instructions on how to include Log4j into their project using their chosen build tool.

```
package com.example;

import org.apache.logging.log4j.Logger;
import org.apache.logging.log4j.LogManager;

public class Example {
    private static final Logger LOGGER = LogManager.getLogger();

    public static void main(String... args) {
        String thing = args.length > 0 ? args[0] : "world";
        LOGGER.info("Hello, {}!", thing);
        LOGGER.debug("Got calculated value only if debug enabled: {}", () -> doSomeCalculation());
    }

    private static Object doSomeCalculation() {
        // do some complicated calculation
    }
}
```

# Documentation
The Log4j 2 User's Guide is available on here : https://logging.apache.org/log4j/2.x/manual/index.html
or as a downloadable PDF : https://logging.apache.org/log4j/2.x/log4j-users-guide.pdf

# Requirements 
Java 8 users should use 2.17.1 or greater.

Java 7 users should use 2.12.4.

Java 6 users should use 2.3.2.

Some features require optional dependencies; the documentation for these features specifies the dependencies.
