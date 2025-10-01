pipeline {
    agent any

    // environment
    environment {
        PATH="/opt/maven/bin:$PATH"
    }

    stages {

        stage("Build") {
            steps {
                echo "Build Job"
                sh "mvn clean package -Dmaven.test.skip=true"
            }
        }

        stage("Test") {
            steps {
                echo "Test Job"
                sh "mvn surefire-report:report"
            }
        }

        // Sonar analysis
        stage("SonarCloud Analysis") {
            environment {
                scannerHome = tool "sandy-sonar-scanner"
            }
            steps {
                withSonarQubeEnv("sandy-sonar-server") {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }

    } // <-- closes stages
} // <-- closes pipeline

