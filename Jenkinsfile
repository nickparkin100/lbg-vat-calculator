pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/nickparkin100/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'SQ-JenkinsTest'
      }
        steps {
            withSonarQubeEnv('instance-student8-jenkins') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}
