pipeline {
    agent any
    tools {
	    maven "MAVEN3"
	    jdk "OracleJDK8"
	}

    stages{
        stage('Fetch code') {
          steps{
              git branch:'devops', url: 'https://github.com/akhilvijay15/vprofile-project.git'
          }  
        }

    

 stage('Static Analysis') {
      withSonarQubeEnv('MySonarToken') 
      {
        bat 'mvn clean package sonar:sonar'
   	echo 'Static Analysis Completed' 
      }
   
    stage("Quality Gate"){
      timeout(time: 1, unit: 'HOURS') 
      {
        waitForQualityGate abortPipeline: true
        def qg= waitForQualityGate()
        if (qg.status!= 'OK'){
          error "Pipeline aborted due to quality gate failure: ${qg.status}"
        }
      }         
      echo 'Quality Gate Passed' 
    }
  } 
}
      
}    