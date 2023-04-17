Maven is a powerful project management tool that is based on POM (project object model). It is used for projects build, dependency and documentation.

#### To compile the project: ####

** mvn compile **
Copy
Maven will run through all lifecycle phases needed by the compile phase to build the project's sources. If you want to run only the test phase, you can use:

** mvn test **
Copy
Now let's invoke the package phase, which will produce the compiled archive jar file:

** mvn package **

## Download and install maven in your local ##

Download maven packages from https://maven.apache.org/download.cgi  
 we are using [Maven-3.8.7](https://dlcdn.apache.org/maven/maven-3/3.8.7/binaries/apache-maven-3.8.7-bin.zip)

1. Setup environment variable. 
    a. Start searching “edit system environment variables” in the windows search, under advance tab chose Environment variables --> under the System variables chose `new..` 
    b. in the dialog box 
     ```sh 
     Variable name: MAVEN_HOME
     Variable value: <MAVEN_PATH>
     in my system jdk location is C:\Program Files\apache-maven-3.8.7
     ```
     ok to save. 
    c. add same to PATH variable. 
    system variables --> select path -->  add new --> 
    <MAVEN_Path>\bin
    _in my system this path location is C:\Program Files\apache-maven-3.8.7\bin

To validate java version, run below command. 
   ```sh 
      mvn -version
   ``` 
Output of above command should be like below 
  ```sh
   Apache Maven 3.8.7 (b89d5959fcde851dcb1c8946a785a163f14e1e29)
   Maven home: C:\Program Files\apache-maven-3.8.7
   Java version: 19.0.1, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk-19
   Default locale: en_IN, platform encoding: UTF-8
   OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
 ```

 ### Building java source code 

1. Build source code  
   go to source code folder and run below command 
   `Note: make sure you have pom.xml in the folder`
   ```sh 
    mvn clean install -Dmaven.test.skip=true  
   ```
 
 Once build is successful you can see 'target' directory in the same location. 
 find your war/jar/ear file inside target folder. 
 
 In this project we could see a war file (login-release.war) in the target folder. 
 
 To run war file we need Apache tomcat. Lets install Apache tomcat