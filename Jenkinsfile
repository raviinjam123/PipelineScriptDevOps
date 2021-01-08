node
{

  def mavenHome = tool name: "maven3.6.2" 
  
  properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

  stage('Checkout')
   {
    git branch: 'development', credentialsId: '04c2e57a-7a93-45af-a74b-870aec19a2a2', url: 'https://github.com/raviinjam123/maven-web-application.git'
   }

  stage('Build')
   {
    sh "${mavenHome}/bin/mvn clean package"
   }
   /*
   stage('ExecuteSonarQubeReport')
    {
     sh "${mavenHome}/bin/mvn sonar:sonar"
    }

  stage('UploadArtifactsIntoNexus')
    {
     sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('DeployAppIntoTomcatServer')
    {
     sshagent(['63c92e40-c0ec-434c-a813-10abeab4680a']) {
       sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@18.188.32.46://opt/apache-tomcat-9.0.41/webapps"
    }
    }
    
    stage('EmailNotification')
    {
     emailext body: '''Build is Over!!

     Regards,
     Ravi Injam.''', subject: 'Build is Over!!', to: 'injam6969@gmail.com'
    }
    
    */
}
