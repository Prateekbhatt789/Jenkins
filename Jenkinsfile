pipeline {
    agent {
        node {
            label "built-in"
        }
    }
    options {
    buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
    }
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Enter the branch to be deployed')
    }
    environment {
        git_url = "https://github.com/Prateekbhatt789/Jenkins.git"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Prateekbhatt789/Jenkins.git'
            }
        }

        stage('Code Build ') {
            steps {
                sh """
                echo 'Code Build Stage'
                """
            }
        }

        stage('Image Build & push ') {
            steps {
                sh '''
                echo 'Image Build & push Stage'
                '''
            }
        }

        stage('Deploy to ECS') {
            steps {
                sh """
                echo 'Deploy to ECS Stage'
                """
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
