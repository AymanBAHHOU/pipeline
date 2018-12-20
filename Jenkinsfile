
pipeline {
    agent any
    tools {
     maven 'Maven 3.6.0'   
     jdk 'jdk 1.8'
    }
    stages {
    stage('Build'){
      steps {
        bat 'mvn clean install'
      }
        post{
            success{
                junit 'target/surefire-reports/**/*.xml'
            }
        }  
    }
    
    stage('Test'){
      steps {
        bat "mvn test"
        bat "mvn cobertura:cobertura -Dcobertura.report.format=html"
      }
    }
    
    stage('Deploy'){
      steps {
        echo 'Deploying ..'
      }
    }
    
  }  
}