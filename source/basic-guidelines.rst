######################################
Basic Style Guidelines - All Languages
######################################

#. First and foremost, whatever code style is chosen be consistent.
    #. This will make comparing changes easier.
#. Don't keep a running a change log in the header of a source file.
    #. There are two reasons for this.
       #. The file is in source control and changes are recorded there.
       #. It can make the diff between versions in source control difficult to compare.
#. Code should be readable.
   #. If you read a section of code aloud, like reading a novel out loud, it should make sense.
#. Have meaningful tests.
   #. This may be unit, functional, or integration tests. A meaningful test exercises as much of the code as possible in a way someone will use it.
#. Try not to go past column 60, prefer not to go past column 80, never go past column 120.
   #. Human beings don't do well reading long lines. Break long if statement logic and function inputs into multiple lines.
#. Don't use acronyms or initialism that aren't in general common usage. For example, ID, is short for identification. Just about everyone uses it.
   #. Avoiding domain jargon allows for easier discussion with people that might be familiar with what your trying to do on a technical level, but may not know your domain.
   #. Additionally you have people fresh to the domain and it shouldn't be needless difficult for them to get into understanding and talking about it.
#. Retrieved variables should be final/const/(whatever read-only marker is appropriate to the language at hand) unless it is known that the value should mutate
   #. NOTE FOR Java: final actually means final for primitive, for non primitives it means the reference will not change for the life of the scope you are in. To further handle "read only" In this case use immutable objects, copies, Collections.immutable, etc.
#. All rules have exceptions, but don't overdo it.

Code Reviews
============

#. Do them. Don't work in isolation if at all possible.
#. If your project has a wide reach, it should be looked at by multiple people. Code reviews can be enforce by various methods
    #. BitBucket - discussion through the pull-request interface on Bitbucket (approve can be used as a merge gate so you know someone looked at it.)
    #. GitHub - use review approvals as a merge gate

Static Analysis
===============

#. SonarQube is a tool that is critical for establishment of code standards. SonarQube is a source code analyzer that can detect bugs, vulnerabilities, and “code smells” in source code. It is established as a web service with a front end operational user interface that ties into source control projects. SonarQube when integrated into developer IDEs allows for code analysis to occur as code is written. The coding standards for CWMS source code has been codified into SonarQube as rules. The default SonarQube rule set, “Sonar Way”, was chosen as a starting point. From this rule set was derived the “RMA Way”. The “RMA Way” was created through collective review of the “Sonar Way” rule set with modifications made to the rules to fit the pre-existing CWMS code guidelines (guidelines as they were not formalized and written down until the “RMA Way” was created). The “CWMS_ATO” rule set is derived from the “RMA Way” and contains modifications specific to the STIG vulnerabilities that have been addressed for the CWMS ATO. Review and modification of SonarQube’s rules occurs periodically with critical changes being made immediately as needed.
#. HEC has sonarqube setup at https://sonarqube.hecdev.net
    #. This contains the default rules which are perfectly acceptable for your project to start with
    #. For CWMS projects make sure after the first analysis that you Switch it to the CWMS ATO profile.
    #. See SonarQube for more information on settings up SonarQube in your project.
    #. Currently Supported language (we are on the free license)
       #. Java
       #. JavaScript
       #. HTML
       #. Python
    #. Public GitHub projects can and should integrate with SonarCloud.

Refactoring
===========

#. What is refactoring?
    #. Refactoring is altering the structure of code to perform the same behavior WITHOUT affecting external components.
#. When to refactor?
    #. As needed when touching legacy code
    #. Don't refactor it unless there's a bug in the code
        #. Counter Point:
          #.  If you can create a test to cover the known cases have at.
          #.  BUT REREAD Refactoring.1.a
        #. File formatting is acceptable when you modify the code
            #. This should not be submitted at the same time as the code changes.
                #. A git pull-request can include changes and format change, but they should be in separate commits
                #. E.G. do the format changes, make a commit, do your code change. (the opposite order is also acceptable.)
        #. Prefer automated processes over manual refactoring - use your IDE wisely
            #. IDE's have a rename and refactor to method action that can be used to reduce accidental logical changes
                #. I'm not sure if there's anything else that would be best to describe - those are the two primaries I use

Rearchitecting
==============

#. This is restructuring your code in a way that may break downstream compatibility
#. When to rearchitect?
    #. preferably never
    #. But whenever your current structure denies you're ability to more forward
#. How to rearchitect
    #. Just do it
    #. Make sure your version goes up a major version (if using semver) or otherwise make it obvious
    #. Plan to support the old version with bug fixes for a while as people transition.

Testing and integrity
=====================

#. Testing (any level) provides for the integrity and documentation of the systems.
    #. It should not be considered an optional requirement or additional expense.
#. Any change SHOULD  include an automated test
#. Any change MUST  at least include a documented test procedure
#. Large changes MUST  include some form of test.
    #. A lack of automated tests must be justified with specific issues.

   