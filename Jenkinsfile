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
                sh label: '', script: 'mvn clean package checksytle:checkstyle'
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