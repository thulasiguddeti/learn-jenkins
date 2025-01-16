pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        GREETINGS = 'Hello Jenkins'
    }
    options{
        timeout(time: 1, unit: 'HOURS')
    }
    // build
    stages {
        stage('Build') { 
            steps {
                echo 'Building...'
            }
        }
        stage('Test') { 
            steps {
                echo 'Testing...' 
            }
        }
        stage('Deploy') { 
            steps {
                sh """
                    echo "here I wrote shell script"
                    echo "$GREETING"
                    sleep 10
                """

            }
        }
    }
    //  post build 
    post {
        always {
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'This runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say hello when pipeline is success'
        }
    }
}
