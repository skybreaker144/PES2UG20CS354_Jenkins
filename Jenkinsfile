pipeline {
  agent any
  stages{
    stage('Build'){
      steps{
        sh 'g++ main/hello.cpp -o output'
        build 'PES2UG20CS354-1'
        echo 'Build  Successful'
      }
    }
    stage('Test'){
      steps{
         sh './tput'
        echo 'Test Successful' 
       
      }
    }
    stage('Deploy'){
     when{
        expression{
          currentBuild.result == null || currentBuild.result == 'SUCCESS'
        }
      }
      steps{
        echo 'Deployment Successful'
      }
  }
}
  post{
    failure{
      echo 'Pipeline failed'
    }
  }
}
