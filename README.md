# Maven_documentation

_Maven Lifecycle_
```
1. init
2. Compile
3. Scope
4. Run
5. End
```
_Maven Cmd_
```
phases

mvn clean    - delete the previously added target files
mvn validate - validates wheather all the files are available within the project
mvn compile  - Compiles only the source code also executes clean & validate
mvn test     - executes the test cases also executes clean, validate, compile 
mvn package  - will generate the jar or war file also executes clean, validate, compile, test & package
mvn install  - will install the jar file in the local maven repository also executes clean, validate, compile, test, package & install
mvn deploy   - will deploy to the remote repository also executes clean, validate, compile, test, package, install & deploy

```

_Plugins_

Note: 
1. Plugin will be placed inside the following tags
   build
    plugins
       plugin
```
1. Compiler - Compile the code
2. Surefire - Execute the TestNG test cases
3. Source   - Will convert code into jar
```
maven surefire plugin
```
<build>
    <pluginManagement>
      <plugins>
        <plugin>
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-surefire-plugin</artifactId>
          <version>3.0.0-M5</version>
          <configuration>
            <suiteXMlFiles>
              <suiteXMlFile>testng.xml</suiteXMlFiles>
            </suiteXmlFiles>
           </configuration>
        </plugin>
      </plugins>
    </pluginManagement>
  </build>
```
Note:
1. In maven project all the test cases or test classes should be in the `src/test/java`

_Maven structure_

Dependencies consists of 
1. groupId
2. artifactId
3. version

_Maven Report_
```
sure fire plugin reports will be in the `target` folder of the project

TestNG reports will be in `test-output` folder
```

_Steps to be followed after creating maven project in eclipse_

1. add dependencies

2. traverse to the location of the project folder in cmd and type `mvn clean install` - will download all the jar files
related to the dependencies and execute the testcases

3. step2 should be done whenever the Pom.xml got change

4. if the pom has no changes can execute `mvn test` from the cmd

5. To get a build without executing the testcase can use `mvn clean install -DskipTest=True` - will download all the jars
alone


