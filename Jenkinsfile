pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw package' 
            }
        }
        stage('test') {
            steps {
                sh './mvnw test' 
            }
        }
        stage('package') {
            steps {
                sh './mvnw package' 
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        success {
            slackSend(color: '#00FF00', message: "Succesful: job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        }
        failure {
            slackSend(color: '#FFF00', message: "Started: job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        }
    }
}
