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
      
    }
  }
  stage("ContinuousTesting")
  {
    steps
    {
      
    }
  }
}
}
