pipeline
{
    agent any
    stages
    {
     stage('CONTINOUS DOWNLOAAD')
     {
         steps
         {
             git 'https://github.com/madhukanth811/maventest1.git'
         }
     }
     stage('CONTINOUS BUILD')
     {
         steps
         {
             sh 'mvn package'
         }
     }
          stage('CONTINOUS DEPLOYMENT')
     {
         steps
         {
             sh 'scp /var/lib/jenkins/workspace/decsam1/webapp/target/webapp.war ubuntu@172.31.4.248:/var/lib/tomcat9/webapps/testapp.war'
         } 
     }
          stage('CONTINOUS TESTING')
     {
         steps
         {
            git 'https://github.com/madhukanth811/test2.git'
           sh 'java -jar /var/lib/jenkins/workspace/decsam1/testing.jar'
         }
     }
     stage('CONTINOUS DELLIVERY')
     {
         steps
         {
             sh 'scp /var/lib/jenkins/workspace/decsam1/webapp/target/webapp.war ubuntu@172.31.4.38:/var/lib/tomcat9/webapps/prodapp.war'
         }
     }
     
    }
}
