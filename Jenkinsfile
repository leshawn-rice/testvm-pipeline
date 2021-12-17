properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any

    stages {
        stage('Fake build') {
            steps {
                echo 'Building....'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
