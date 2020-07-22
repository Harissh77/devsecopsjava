pipeline {

agent any 
tools 
{
  maven 'maven'
}

stages 
{
  stage('checking maven installation')
  {
    steps
    {
       sh 'mvn -v'
    }
  }
  stage('Security Check')
  {
    steps
    {
       sh 'docker run  --rm  gesellix/trufflehog --json  https://github.com/Harissh77/devsecopsjava.git > bug.log'
       sh 'bug.log'
    }
  } 
  stage('Build Java Project')
  {
    steps
    {
       sh 'mvn clean package'
    }
  }  
}
}
