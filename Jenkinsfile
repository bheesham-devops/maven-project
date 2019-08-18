pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }

            post{
                success {
                echo "Showing Trend for Junit separately"
                junit '**/surefire-reports/*.xml'
                archiveArtifacts '**/*.war'
                }
                
            }
        }

        stage('Deploy') {
            steps {
                timeout(time: 90, unit: 'SECONDS') {
                input 'Are you sure to deploy it?'
                }
            echo "This is Deployment Stage"
            build 'dev-deploy'
            }
        }
    }
}