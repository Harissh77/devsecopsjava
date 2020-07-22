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
       sh 'docker run --rm  ashu:secv1'
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
