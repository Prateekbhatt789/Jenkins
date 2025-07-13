pipeline {
    agent {
        node {
            label "master"
        }
    }
    options {
    buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
    }
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'master', description: 'Enter the branch to be deployed')
    }
    environment {
        git_url = "git@github.com:Prateekbhatt789/Jenkins.git"
    }

    stages {
        stage('Code Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '${BRANCH_NAME}']], extensions: [], userRemoteConfigs: [[credentialsId: '4e', url: git_url]]])
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
