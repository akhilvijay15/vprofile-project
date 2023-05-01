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

        sonarcube scanner for maven => 

node {
  stage('SCM') {
    git 'https://github.com/akhilvijay15/vprofile-project.git'
  }
  stage('SonarQube analysis') {
    withSonarQubeEnv('sonar') {
      // requires SonarQube Scanner for Maven 3.2+
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
    }
  }
}

    } 
    }