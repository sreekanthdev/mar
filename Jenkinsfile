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
      git 'mvn package'
    }
  }
}
}
