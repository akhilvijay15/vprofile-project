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

        
  stage('Compile-Package'){
  //get maven home path 
  def mvnhome = tool name: 'maven-3', type: 'maven'
  sh "${mvnhome}/bin/mvn package"
  }
  
  stage('SonarQube Analysis') {
  def mvnhome = tool name: 'maven-3', type: 'maven'
  withSonarQubeEnv('MySonarToken') {
  sh "${mvnHome}/bin/mvn sonar:sonar"
  }
}

    }
}