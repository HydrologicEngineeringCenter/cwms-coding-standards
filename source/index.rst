.. CWMS Coding Standards and Guidance documentation master file, created by
   sphinx-quickstart on Wed Apr 16 13:47:48 2025.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

CWMS Coding Standards and Guidance documentation
================================================

Standards, Guidance, and Templates for CWMS Projects.

Coding standards establish a recognized set rules, configurations, and practices that a team follows to write consistent source code. A goal of coding standards is to have any given programmer implement code that is understandable, maintainable, and extensible by all of the other members of the team. There is a corresponding reduction in the number of bugs introduced given this better understanding of each other’s code.

It is important that the development team adopt one single coding standard because it allows the team to be able to freely work on any part of the source code. It frees the team from having to follow the original author’s personal standards when modifying a source code.

Don’t start from scratch, use something that already exists and customize it for your needs.

Doesn’t concern source code only, covers practices, tools, and conventions that add benefit to the code base.

Quantitative vs Qualitative

It is ok to constructively disagree as long as the coding standards are built on consensus. The standards are intended to be amended and improved. Minimal set of standards focused on consistency and consensus over perfection. There are more important things to do than argue about formatting.

Coding standards meetings.

Agree, will go along with consensus, disagree and explain why.

If A vs B and a decision cannot be made, try one or both out and find out if it they correct or not. Leave A and B out of the standard until the determination is made. Coding standards should not be a divisive issue for a development team.

Deviations from a standard are accepted as coding standards are not requirements. A coding standard should not be a substitute for a developer’s professional judgement. When deviations occur frequently for a given standard, the standard might need to be changed as it is possible that the standard is not suitable for all circumstances.

Standards should be automated as much as possible through the use of formatters and code analyzers.

Standards should be defined independent of programming languages as much as possible to ensure that coverage is as universal as possible across all languages.

Evaluate standards as work occurs to identify those which should be modified.

Be cautious when changing a standard as doing so could result in code that followed the previous standard no longer being compliant

Standards need to be easily accessed. Discourse.

Code reviews should check if standards are being followd

Legacy Code
-----------

Legacy code should be left alone if it works and there is no reason to read or modify it. Upfront modification of legacy code to meet the standard is expensive in terms of time and risk. When legacy code needs modification, refactor the sections of the code being worked on to bring them up to the current standard. I.e. follow the coding standards on all new code and modifications to existing code.


Additional Resources
--------------------


#. Martin Fowler, clean code, cleaner code (https://www.amazon.com/dp/0132350882), (https://martinfowler.com/eaaCatalog/)
#. CMU Software Engineering Institute (https://wiki.sei.cmu.edu/confluence/display/java/Java+Coding+Guidelines)
#. https://www.adventureswithagile.com/2014/05/28/coding-standards/
#. https://www.jamesshore.com/Agile-Book/coding_standards.html
#. https://dzone.com/articles/how-to-successfully-apply-coding-standards
#. http://agileinaflash.blogspot.com/2009/02/coding-standards.html
#. Google Coding standards (https://google.github.io/styleguide/javaguide.html)
#. Oracle Coding Standards (https://www.oracle.com/technetwork/java/codeconventions-150003.pdf)
#. Extreme Programming Wiki reference (https://en.wikipedia.org/wiki/Extreme_programming_practices#Coding_standard)


.. toctree::
   :maxdepth: 2
   :caption: Guidelines


   Basic Guidelines <./basic-guidelines.rst>

.. toctree::
   :maxdepth: 1
   :caption: Language Guidelines

   Java <./guidelines-java.rst>