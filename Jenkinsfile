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



    }
}