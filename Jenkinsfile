pipeline
{
 agent any
 stages{
  stage('Build Application'){
  steps{
  bat 'mvn clean install'
  }
  }
  
   stage('Deploy Application to Mulesoft Cloudhub'){
   steps{
   bat 'mvn package deploy -DmuleDeploy'
  }
 }
  stage('Perform Regression Testing'){
  steps{
  bat'newman run C:\\newman\\mulehealthcareproject.postman_collection.json --disable-unicode'
  }
  
  }
  
 }
 
}