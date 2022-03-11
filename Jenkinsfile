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
}
