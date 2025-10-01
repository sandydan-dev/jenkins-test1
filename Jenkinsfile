pipeline {
  agent any

  // environment
  environment {
    PATH="/opt/maven/bin:$PATH
  }

  // stage block start
  stages {
    
    stage("build"){
      steps{
        echo "Build Job"
        sh "mvn clean package" 
      }
    }

    stage("test"){
      steps{
        echo "Test Job"
      }
    }
    
   // sonar analysis
   stage("Sonarqube Analysis"){
      environment {
         scannerHome = tool "sandy-sonar-scanner"
      }

      // steps to sonar server
      steps {
        withSonarQubeEnv("sandy-sonar-server"){
           sh "${scannerHome}/bin/sonar-scanner"
        }
      }
   }
    
  // statge block end

}
