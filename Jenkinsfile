pipeline {
    agent any
    environment {
        ENV_VAR = "pipeline.google.com"  // If we declare here it is pipe line leval variable
        SSH_CRED = credentials('SSH_CRED')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('one') {
            steps {
                sh '''
                echo Hello World-stage-1
                echo pipeline var = ${ENV_VAR}
                env
                '''
            }
        }
        stage('Two') {
            environment {                  
            ENV_VAR = "pipeline-stage.google.com"  // if we declare here it is a stage variable 
            }

            steps {
                sh '''
                echo Hello World-stage-2
                echo pipeline var = ${ENV_VAR}
                '''
                
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