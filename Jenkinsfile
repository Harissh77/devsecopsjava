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
      
       sh 'docker run  --rm  gesellix/trufflehog --json  https://github.com/Harissh77/devsecopsjava.git > bug.txt'
       sh 'cat bug.txt'
       
      
    }
  } 
 
  stage('Build Java Project')
  {
    steps
    {
       sh 'mvn clean package'
    }
  }  
 stage('Connecting Ansible')
  {
    steps
    {
       sh 'ansible tomcat -u root -m ping'
       
    }
  }
 stage('Adding War file')
  {
    steps
    {
       sh 'ansible-playbook tomcatdeploy.yml'
    }
  }
}
}
