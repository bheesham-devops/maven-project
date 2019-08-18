pipeline{
    agent any
    tools {
        maven 'Maven_3'
        jdk 'Java_8'
    } 
        stages {
        stage('init') {
            steps{
                echo "This is initializing stage"
                sh label: '', script: 'mvn clean package checkstyle:checkstyle'
                echo "Show CheckStyle Error in Graph"
                checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''
                echo "Showing Trend for Junit separately"
                junit '**/surefire-reports/*.xml'
            }
        }

        stage('build') {
            steps{
                echo "This is initializing stage"
            }
        }

        stage('Deploy') {
            steps {
            echo "This is Deployment Stage"
            }
        }
    }

}