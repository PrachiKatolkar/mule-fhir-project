pipeline
{
 agent any
 stages{
  stage('Build Application'){
  steps{
  bat 'mvn clean install'
  }
  }
  
 stage('SonarQube Testing'){
 steps{
 bat 'mvn sonar:sonar -Dsonar.sources=src/ -Dsonar.host.url=http://localhost:9000 -Dsonar.login=0df219b9363898bb5517ef7af3f5e21553b71405'
 }
 }
  
   stage('Deploy Application to Mulesoft Cloudhub'){
   steps{
   bat 'mvn package deploy -DmuleDeploy'
  }
 }
 
  stage('Perform Regression Testing'){
  steps{
  bat'C:\\Users\\pkatolka\\AppData\\Roaming\\npm\\newman run C:\\newman\\mulehealthcareproject.postman_collection.json --disable-unicode'
  }
  
  }
  
 }
 
}