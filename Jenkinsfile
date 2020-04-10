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
}
}
