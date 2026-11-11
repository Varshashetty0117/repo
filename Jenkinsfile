pipeline{
  agent any
  triggers{githubPush()}

  stages {
    stage('Ceckout'){
      steps{'checkout scm
           }
    }
    stage('Build'){
      steps{bat 'javac -version'
            bat 'javac App.java AppTest.java'
           }
    }
    stage('Test'){
      steps{ bat 'java AppTest'
           }
    }
  }
      post{
        success{echo 'Build stable'}
        failure{echo 'Build failed'}
      }
}
