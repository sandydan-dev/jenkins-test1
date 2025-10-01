pipeline {
  agent any

  // stage block start
  stages {
    
    stage("build"){
      steps{
        echo "Build Job"
        sh "date"
        sh "cal"
      }
    }

    stage("test"){
      steps{
        echo "Test Job"
      }
    }

    stage("deploy"){
        echo "Deploy Job"
    }

  }
  // statge block end

}
