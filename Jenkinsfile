node {
   
   stage('Code Checkout') { 
     git credentialsId: 'githubID', url: 'https://github.com/itrainjaquar/maven-examples.git'
     
    }
   stage('Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn clean compile'
      }
    }
   stage('Unit Test run') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn test'
      } 
    }
   stage('Sonarqube analysis'){
     withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn org.jacoco:jacoco-maven-plugin:prepare-agent package sonar:sonar' +
             ' -Dsonar.host.url=https://sonarcloud.io '+
             ' -Dsonar.organization=itrainjaquar '+ 
             ' -Dsonar.login=20fdaa406963ab00719d979d512a587c9207c8a7 '   
        
     }  
    }
  stage("Quality Gate"){
          
    }
   stage('Package to Jfrog') {
    
    }
   
   stage('Deploy to Dev') {
     
    }
   stage('Automation Testing') {
     
    }
   stage('Deploy to Test') {
     
    }
   stage('Smoke Testing') {
     
    }
   stage('Deploy to Prod') {
     
    }
   stage('Acceptance Testing') {
     
    }
}
