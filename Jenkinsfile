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
                ansiblePlaybook(
                  playbook: 'playbook.yml',
                  inventory: 'inventory.ini',
                  extraVars: [
                      ansible_become_pass: [
                          value: """${sh(
                            returnStdout: true,
                            script: 'cat /home/leshawn/.ssh/become_pass'
                          )}""",
                          hidden: true
                      ]
                  ]
              )

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
