Maven official page 
```
[https://www.jenkins.io/download/](https://maven.apache.org/download.cgi)
```
Downloading and Installing Maven
```
wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz
```
Extarcting the maven tar file
```
tar -xvzf apache-maven-3.9.6-bin.tar.gz
```
Renaming the extracted directory
```
mv apache-maven-3.9.6 maven
```
Java 11 (OpenJDK version 11) on Amazon Linux using the amazon-linux-extras
```
amazon-linux-extras install java-openjdk11
```
Configuring Maven and Java environment variables
```
vi ~/.bash_profile
```
```
Add the following lines to the file:
M2_HOME=/opt/maven
M2=/opt/maven/bin
JAVA_HOME=/usr/lib/jvm/java-11-openjdk-11.0.22.0.7-1.amzn2.0.1.x86_64
PATH=$PATH:$HOME/bin:$M2_HOME:$M2:$JAVA_HOME
```

Applying the changes
```
source ~/.bash_profile
echo $PATH
```

Verifying whether maven installed
```
mvn -v
```

