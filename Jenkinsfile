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
  stage('Build Java Project')
  {
    steps
    {
       sh 'mvn clean package'
    }
  }  
}
}
