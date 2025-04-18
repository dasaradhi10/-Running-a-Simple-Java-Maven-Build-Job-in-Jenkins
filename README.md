# Hello Java Maven with Jenkins

This project demonstrates how to set up a simple Java Maven application and use Jenkins to automate the build process with Continuous Integration (CI). The application is a basic "Hello World" program written in Java and built using Maven.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Setup Instructions](#setup-instructions)
3. [Running the Project](#running-the-project)
4. [Jenkins Setup](#jenkins-setup)
5. [Commands Used](#commands-used)
6. [Final Output](#final-output)

## Prerequisites
- **JDK 8 or 11**: Java Development Kit must be installed on your local machine.
- **Maven**: Apache Maven 3.x or later.
- **Jenkins**: Installed locally or on a server.
- **Git**: To manage your repository and clone it from GitHub.

### To install JDK:
- **Windows**: [Download JDK from Oracle](https://www.oracle.com/java/technologies/javase-downloads.html)

### To install Maven:
- **Windows**: [Download Apache Maven](https://maven.apache.org/download.cgi) and follow the installation instructions.

## Setup Instructions

1. **Clone the GitHub Repository**:
   - Clone the project repository from GitHub to your local machine:
     ```bash
     git clone https://github.com/yourusername/hello-java-maven.git
     ```

2. **Project Structure**:
   The project contains the following files:
   hello-java-maven/
   ├── src/ │
     └── main/ │
       └── java/ │
           └── HelloWorld.java
             ├── pom.xml

Modify "HelloWorld.java" file
edit 'src/main/java/HelloWorld.java' to ensure it conatain the following simple java cokde:

public class HelloWorld{
  public static void main (string[] args){
      system.out.println("Hello, jenkins + Maven!");
  }
}

4 Create pom.xml: This is the Maven configuration file that will handle building the project. The content of pom.xml should look like this:
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>

Running the Project
1.Run Maven Build Locally: In your project directory, run the following Maven command to build the project:
mvn clean package

2.Check the Output: If everything works correctly, the output should show a BUILD SUCCESS message:
[INFO] BUILD SUCCESS

3.Run the Java Program: To run the compiled .jar file, execute the following:
java -cp target/hello-1.0.jar HelloWorld


Jenkins Setup
Step-by-Step Guide for Jenkins:

1.Create a New Jenkins Job:
From the Jenkins Dashboard, click New Item.
Enter hello-java-maven-job as the job name.
Select Freestyle project, then click OK.

2.Configure Source Code Management:
Under the Source Code Management section, select Git.
Enter your repository URL:
https://github.com/yourusername/hello-java-maven.git
If it's a private repository, add your GitHub credentials.

3. Add Build Step:
Under Build, click Add build step and select Invoke top-level Maven targets.
In the Goals field, enter clean package.

4.Save and Build:
Click Save.
Trigger the build by clicking Build Now on the project page.

5.Check the Console Output:
After the build completes, click on the build number (e.g., #1), then view the Console Output.
If everything is configured correctly, the output should show BUILD SUCCESS.

Commands Used:

Clone GitHub Repository:
git clone https://github.com/yourusername/hello-java-maven.git

Run Maven Build:
mvn clean package

Run Java Program:
java -cp target/hello-1.0.jar HelloWorld

Final Output
Once the build is successful, the Jenkins Console Output will display:

[INFO] BUILD SUCCESS

---------------------------------------------------------------------------------------------------------------------------------------------------------------


