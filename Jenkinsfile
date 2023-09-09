pipeline {
    agent any
    environment{
        ENV_VAR = "pipeline.google.com"
    }

    stages {
        stage('one') {
            steps {
                sh '''
                echo Hello World-stage-1
                echo pipeline var = {{ENV_VAR}}
                '''
            }
        }
        stage('Two') {
            steps {
                sh "echo Hello World-stage-2"
            }
        }
        stage('Three') {
            steps {
                sh "echo Hello World-stage-3"
            }
        }
        stage('Four') {
            steps {
                sh "echo Hello World-stage-4"
            }
        }
    }
}