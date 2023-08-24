pipeline {
    agent any
    environment {
        name = 'Maihar'
    }
    parameters {
        string (name: 'persion', defaultValue: 'Maihar das', description: 'who are you')
        booleanParam (name: 'isMale', defaultValue: true, description: '')
        choice (name: 'City', choices: ['Delhi','DelhiNCR','Noida' ], description: '')
    }

    stages {
        stage('Run a command') {
            steps {
               sh 'pwd'
               sh 'date'
            }
        }
        stage('environment Variable') {
            steps {
                sh 'echo "$BUILD_ID"'
                sh 'echo "$name"'
                sh 'echo "$username"'
            }
        }
        stage('Parameter') {
            steps {
                echo 'Hello World'
                sh 'echo "$name"'
                sh 'echo "$persion"'
            }
        }
        stage('Continue ?') {
            input {
                message 'Should we continue'
                ok 'Yes we should'
            }
            steps{
                echo 'display in prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        } 
    }
    post { 
            always { 
                 echo 'I will always say Hello again!'
            }
              failure { 
                  echo 'Failure!'
                }
              success { 
                  echo 'Success!'
            }
        } 
}

