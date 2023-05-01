pipeline {
  agent any
  tools {
      maven "MAVEN3"
      jdk "OracleJDK8"
  }
  stages {
       stage('Fetch code'){
          steps {
              git branch:'vp-rem', url: 'https://github.com/akhilvijay15/vprofile-project.git'
          }
       }

       stage('Build'){
          steps{
             sh 'mvn install'
          }
          
             }
          }
       }
       stage('TEST'){
          steps{
             sh 'mvn test'
          }
        }     


