pipeline{
    agent any
    stages{
        stage("Sonarqube Quality check"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonartoken') {
                        sh 'chmod +x gradlew'
                        sh 'sh -x gradlew sonarqube --scan'
                    }
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
    }
}
