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
       sh 'mnv -v'
    }
  }
}
}
