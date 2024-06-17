pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        GREETING = 'Hello Jenkins'
    }
    options {
        timeout(time: 1, unit: 'SECONDS')
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
         stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
          stage('Deploy') {
            steps {
                sh """
                 echo "Here I wrote shell script"
                 echo "$GREETING"
                 sleep 10
                 """
            }
        }
    }
    // post build
    post {
        always {
            echo 'I will always say hello again'
        }
        failure {
            echo 'This runs when pipe;line is failed,used generally to send some alerts'
        }
        success {
            echo 'I will say Hello when pipeline is success '
        }
    }
}