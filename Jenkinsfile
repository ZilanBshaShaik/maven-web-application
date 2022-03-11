node
{
    def MAVEN_HOME = tool name: "maven3.8.4"
    
stage ('checkout')
{
git branch: 'development', credentialsId: 'ec09e576-8b16-41f0-8720-a4fc2167b7ad', url: 'https://github.com/ZilanBshaShaik/maven-web-application.git'
}

stage ('Build')
{
sh "${MAVEN_HOME}/bin/mvn clean package"
}

stage ('Execute SonarQube Report')
{
sh "${MAVEN_HOME}/bin/mvn clean sonar:sonar"
}

stage ('Upload artifact into Nexu repo')
{
sh "${MAVEN_HOME}/bin/mvn clean deploy"
}
/*
stage ('Deploy into tomcat server')
{
sshagent(['8464c40a-c1cd-452a-988f-88f26e348594']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@34.224.32.120:/opt/apache-tomcat-10.0.17/webapps"
}
*/
}
}
