AntRun: a general-purpose Ant build script
==========================================

[![Build Status](https://semaphoreci.com/api/v1/projects/5eab613c-29af-43c0-8961-0170588f6368/466366/badge.svg)](https://semaphoreci.com/sylvainhalle/antrun)

AntRun is a template structure for Java projects. Through its comprehensive
Ant build script, it supports automated execution of unit tests, generation
of [Javadoc](http://www.oracle.com/technetwork/articles/java/index-jsp-135444.html)
documentation and code coverage reports (with
[JaCoCo](http://www.eclemma.org/jacoco/)), and download and installation
of JAR dependencies as specified in an external, user-definable XML file.
It also includes a boilerplate `.gitignore` file suitable for an Eclipse
project.

Table of Contents                                                    {#toc}
-----------------

- [Quick start guide](#quickstart)
- [About the author](#about)

Quick start guide                                             {#quickstart}
-----------------

1. First make sure you have the following installed:

  - The Java Development Kit (JDK) to compile. AntRun was developed and
    tested on version 7 of the JDK, but it is probably safe to use any
    later version.
  - [Ant](http://ant.apache.org) to automate the compilation and build
    process

2. Download the AntRun template from
   [GitHub](https://github.com/sylvainhalle/AntRun) or clone the repository
   using Git:
   
   git@github.com:sylvainhalle/AntRun.git

3. Override any defaults, and specify any dependencies your project
   requires by editing `config.xml`. In particular, you may want
   to change the name of the Main class.

4. Start writing your code in the `Source/Core` folder, and your unit
   tests in `Source/CoreTest`. Optionally, you can create an Eclipse
   workspace out of the `Source` folder, with `Core` and `CoreTest` as
   two projects within this workspace.

5. Use Ant to build your project. To compile the code, generate the
   Javadoc, run the unit tests, generate a test and code coverage report
   and bundle everything in a runnable JAR file, simply type `ant` (without
   any arguments) on the command line. If dependencies were specified in
   step 4 and are not present in the system, they will be downloaded and
   automatically installed. Otherwise, use one of the many [tasks](#tasks)
   that are predefined.

Available tasks                                                    {#tasks}
---------------

This document is incomplete. Execute

   $ ant -p

from the project's top folder to get the list of all available targets.

### dist

The default task. Currently applies `jar`.

### compile

Compiles the project.

### compile-tests

Compiles the unit tests.

### jar

Compiles the project, generates the Javadoc and creates a runnable JAR,
including the sources and the documentation.

### test

Performs tests with jUnit and generates code coverage report with JaCoCo.
The unit test report (in HTML format) is available in the `test/junit`
folder (which will be created if it does not exist). The code coverage
report is available in the `test/coverage` folder.

About the author                                                   {#about}
----------------

AntRun was written by [Sylvain Hallé](http://leduotang.ca/sylvain),
associate professor at [Université du Québec à
Chicoutimi](http://www.uqac.ca/), Canada.
