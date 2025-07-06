pipeline {
    agent { label 'AGENT-1' }

    environment {
        PROJECT = 'EXPENSE'
        COMPONENT = 'BACKEND'

    }
    options { disableConcurrentBuilds() 
              timeout(time: 30, unit: 'MINUTES')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    } 

    stages {
        stage('Build') {
            steps {
               script{
                 sh """
                    echo "Hello, this is build"

                    echo "trigger"

                    echo "Project: $PROJECT"

                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
                 """
               }
            }
        }
        stage('Test') {
            steps {
                script{
                 sh """
                    echo "Hello, this is test"
                 """
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                 sh """
                    echo "Hello, this is deploy"
                    
                 """
                }
            }
        }
    }
    post { 
            always { 
             echo 'I will always say Hello again!'
        }
            failure { 
             echo 'I will run when pipeline failed'
        }
            success { 
             echo 'I will run when pipeline success'
        }
    }
}