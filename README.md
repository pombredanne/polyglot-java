# polyglot-java [![Build Status](https://api.travis-ci.org/vakuum/polyglot-java.png?branch=master)](http://travis-ci.org/vakuum/polyglot-java)

polyglot-java demonstrates how to integrate different JVM languages into a multi-module Maven build.

## Covered Languages

* Clojure (http://clojure.org/)
* Groovy (http://groovy.codehaus.org/)
* Java (http://java.oracle.com/)
* Kotlin (http://jetbrains.com/kotlin/)
* Python (http://www.jython.org/)
* Ruby (http://jruby.org/)
* Scala (http://www.scala-lang.org/)
* Xtend (http://www.eclipse.org/xtend/)

## Requirements

### Java 1.6.0

	$ export JAVA_HOME=/opt/jdk-1.6.0
	$ export PATH=$JAVA_HOME/bin:$PATH

	$ java -version
	java version "1.6.0_45"
	...

* [Java](http://www.oracle.com/technetwork/java/)
* [Java Download](http://www.oracle.com/technetwork/java/javase/downloads/)

### Maven 3.0

	$ export M2_HOME=/opt/maven-3.0
	$ export PATH=$M2_HOME/bin:$PATH

	$ mvn --version
	Apache Maven 3.0.5 (r01de14724cdef164cd33c7c8c2fe155faf9602da; 2013-02-19 14:51:28+0100)
	...

* [Maven](https://maven.apache.org/)
* [Maven Download](https://maven.apache.org/download.cgi)
* [Maven Installation Instructions](https://maven.apache.org/download.cgi#Installation_Instructions)

## Usage

	$ git clone https://github.com/vakuum/polyglot-java.git

### Execute

	$ cd polyglot-java
	$ cat all/src/main/java/polyglot/All.java
	$ mvn clean install -DskipTests
	$ mvn exec:java --projects all
	...
	Hello, I am Java!
	Clojure: Hello Java!
	Groovy: Hello Java!
	Java: Hello Java!
	Kotlin: Hello Java!
	Python: Hello Java!
	Ruby: Hello Java!
	Scala: Hello Java!
	Xtend: Hello Java!
	...

### Execute a specific module

	$ cd polyglot-java
	$ mvn clean install -DskipTests
	$ mvn exec:java --projects clojure
	...
	Clojure: Hello Clojure!
	...

	$ mvn exec:java --projects groovy
	...
	Groovy: Hello Groovy!
	...

	$ mvn exec:java --projects java
	...
	Java: Hello Java!
	...

	$ mvn exec:java --projects kotlin
	...
	Kotlin: Hello Kotlin!
	...

	$ mvn exec:java --projects python
	...
	Python: Hello Python!
	...

	$ mvn exec:java --projects ruby
	...
	Ruby: Hello Ruby!
	...

	$ mvn exec:java --projects scala
	...
	Scala: Hello Scala!
	...

	$ mvn exec:java --projects xtend
	...
	Xtend: Hello Xtend!
	...

### Executable JAR

	$ cd polyglot-java
	$ mvn clean install -DskipTests
	$ mvn assembly:assembly --projects all -DskipTests
	$ java -jar all/target/polyglot-java.jar
	...
	Hello, I am Java!
	Clojure: Hello Java!
	Groovy: Hello Java!
	Java: Hello Java!
	Kotlin: Hello Java!
	Python: Hello Java!
	Ruby: Hello Java!
	Scala: Hello Java!
	Xtend: Hello Java!
	...

### Tests

	$ cd polyglot-java
	$ cat all/src/test/java/polyglot/TestAll.java
	$ mvn clean install -DskipTests
	$ mvn test --projects all
	...
	Tests run: 9, Failures: 0, Errors: 0, Skipped: 0
	...

## License

Copyright (c) 2012-2013 Clemens Fuchslocher, released under the MIT license.
