pipeline
{
agent any
stages
{
  stage("ContinuousDownload")
  {
    steps
    {
      git 'https://github.com/selenium-saikrishna/maven.git'
    }
  }
  stage("ContinuousBuild")
  {
    steps
    {
      sh 'mvn package'
    }
  }
   stage("ContinuousDeployment")
  {
    steps
    {
      sh 'scp /home/ubuntu/.jenkins/workspace/dpipeline/webapp/target/webapp.war ubuntu@172.31.47.37:/var/lib/tomcat8/webapps/qaenv6.war'
    echo "Deployment pass!!"
    }
  }
  stage("ContinuousTesting")
  {
    steps
    {
      git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
      echo "Testing pass"
    }
  }
  post
  {
    success
    {
            sh 'scp /home/ubuntu/.jenkins/workspace/dpipeline/webapp/target/webapp.war ubuntu@172.31.33.83:/var/lib/tomcat8/webapps/prodenv6.war'
    }
    failure
    {
      mail bcc: '', body: 'this build is failed with technical issues', cc: '', from: '', replyTo: '', subject: 'Build', to: 'sreekanthbujji24@gmail.com'
    }
  }
}
}
