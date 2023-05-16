pipeline
{
    agent any
    stages
    {
     stage('CONTINOUS DOWNLOAD')
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
             deploy adapters: [tomcat9(credentialsId: '2679f672-cf04-4c01-8265-bf657e86db6b', path: '', url: 'http://172.31.4.248:8080')], contextPath: 'testapp', war: '**/*.war'
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
             deploy adapters: [tomcat9(credentialsId: '2679f672-cf04-4c01-8265-bf657e86db6b', path: '', url: 'http://172.31.14.23:8080')], contextPath: 'prodapp', war: '**/*.war'
         }
     }
     
    }
}
