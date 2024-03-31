java
***************************************************
sudo -i
sudo yum install java-1.8.0-openjdk -y
// sudo update-alternatives --config 'java'  -->  find java home  --> /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.402.b06-2.el9.x86_64
// JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.402.b06-2.el9.x86_64
/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.402.b06-2.el9.x86_64
--------------
sudo yum install java-17-openjdk -y
// sudo update-alternatives --config 'java'  -->  find java home  --> /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.402.b06-2.el9.x86_64
// JAVA_HOME=/usr/lib/jvm/java-17-openjdk-17.0.10.0.7-2.el9.x86_64
-------------------

// PATH=$PATH:$HOME/bin:$JAVA_HOME
// source ~/.bash_profile
***************************************************
jenkins

set java variable in jenkins
// manage jenkins -> global tools -> jdk -> java home

maven
***************************************************
wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz

tar -xvzf apache-maven-3.9.6-bin.tar.gz
// M2_HOME=/opt/apache-maven-3.9.6
// M2=/opt/apache-maven-3.9.6/bin
// PATH=$PATH:$HOME/bin:$JAVA_HOME:$M2:$M2_HOME


sonarqube
****************************************************
download sonarqube.zip in /opt/
unzip
create an mysql rds instance
   database-1
   postgres
   Ym0HYLhTllGsTVi27BIW
// psql --host=database-1.c122ykskkk0j.us-east-1.rds.amazonaws.com --port=5432 --username=postgres --dbname=database-1
   
   create db in postgresql
   //CREATE DATABASE sonar WITH ENCODING='UTF8';



   create database for mysql
   //CREATE DATABASE sonar CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   //CREATE USER 'sonar'@'localhost' IDENTIFIED BY 'sonar';
   //CREATE USER 'sonar'@'%' IDENTIFIED BY 'sonar';
   //GRANT ALL PRIVILEGES ON sonar.* TO 'sonar'@'%';
   //GRANT ALL PRIVILEGES ON sonar.* TO 'sonar'@'localhost';


   edit sonarqube -> conf -> sonar.properties
   database username and password

   edit java home
   SONAR_JAVA_PATH=/usr/lib/jvm/java-1.8.0-openjdk


   sonarqube with containers
   //docker run -d --name postgres -e POSTGRES_USER=sonarqube -e POSTGRES_PASSWORD=sonarqube -e POSTGRES_DB=sonarqube -p 5432:5432 postgres:latest

   //docker run -d --name sonarqube --link postgres -e SONARQUBE_JDBC_URL=jdbc:postgresql://postgres:5432/sonarqube -e SONARQUBE_JDBC_USERNAME=sonarqube -e SONARQUBE_JDBC_PASSWORD=sonarqube -p 9000:9000 sonarqube:latest

   //create token in sonarqube server
   //add sonar token to jenkins secret text





nexus
