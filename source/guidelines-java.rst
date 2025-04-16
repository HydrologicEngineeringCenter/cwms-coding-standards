====
Java
====


Project Setup
=============

Use a build tool such as Maven, Gradle, or Ant. IDE based project management makes automated builds difficult and can lead to accidentally making some configuration element dependent on your machine.

NOTE: Gradle is preferred, use for any new projects.

Code
====

#. follow https://google.github.io/styleguide/javaguide.html
#. Fail fast, fail hard, but be descriptive
#. Focus on priority. If code has a given priority the standards can be bent. For example, code that needs to perform given operations as fast as possible might structure data in large primitive arrays instead of using Java’s collections API in order to provide fast access to a contiguous block of memory. 
#. Handling Null
    #. No null collections (always initialize)
    #. If appropriate for your project use `@NotNull` for inputs if they absolutely can't be null. (they will require extra dependencies. We may make an HEC standard annotation library... there's a lot of options in the wild)

        .. code-block:: java

            public void setObject( @NotNull Object theInput){
            ...
            }


    #. Otherwise use Object.requireNonNull

        .. code-block:: java

            import static java.util.Objects.requireNonNull;

                public class Role {

                private final UUID guid;
                private final String domain;
                private final String name;
                private final Optional<String> description;

                public Role(UUID guid, String domain, String name, Optional<String> description) {
                    this.guid = requireNonNull(guid);
                    this.domain = requireNonNull(domain, "Domain is required");
                    this.name = requireNonNull(name);
                    this.description = requireNonNull(description);
                }


Documentation
=============

#. Javadocs 
    #. Standardized class JavaDoc
        #. Author tag
    #. Class Header (copyright stuff before the package statement)
        #. Goes above the package statement
        #. Sample:

           .. code-block:: java

               /*
                * Copyright (c) 2020
                * United States Army Corps of Engineers - Hydrologic Engineering Center (USACE/HEC)
                * All Rights Reserved.  USACE PROPRIETARY/CONFIDENTIAL.
                * Source may not be released without written approval from HEC
                */

    #. For entirely US Gov't Employee created works and approved for open source/github follow the guidance at https://code.mil/how-to-open-source.html
    #. Otherwise use the following

       .. code-block:: java

            /*
            Written by US Gov't Employees. Do not release without permission from at least the division chief of team originating this software.
            */


    #. Public required
    #. When using the Deprecated annotation, always specify either a version of the software, or a date.
    #. Protected optional (?)
    #. Fill out all content
    #. UI code (should this be JavaDoc'd?)

Error Handling
==============

#. When to handle Exceptions
    #. UI elements, data models, places where the exception is important.
    #. Always log the exception, even if you are intentionally throwing it away.
#. When to throw Exceptions
    #. DB calls
    #. requireNonNull(Object obj, String message)
        #. Provides way to fail early on things that should never be null, and allows for meaningful message.
        #. See handling null in code section above
    #. When to create custom Exceptions
        #. Caught
        #. Runtime
    #. Do not throw new RuntimeException();
        #. Find or create a more descriptive exception that can be caught if needed.
#. Prefer high detail information in Exceptions

Logging
=======

#. When and Where
#. Log Levels and their meanings
    #. What's seen by the end user
    #. What's not seen by the end user
#. No null messages
#. How to attach stack trace to the log

    #. log(Level.INFO, "Message", ex); - correct because it can log the stack trace
    #. log(Level.INFO, "Message " + ex.getMessage()); - not correct because it only logs the message

Tests
=====

New projects should use junit 5. The support for parameterized tests is better than junit 4.