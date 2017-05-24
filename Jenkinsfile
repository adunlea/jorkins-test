pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                checkout scm
                echo 'Building..'
                echo "branch: ${env.BRANCH_NAME}"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            when { 
                branch 'production' 
            }
            steps {
                echo 'Deploying...'
            }
        }
        stage('Dance Party') {
            steps {
                echo 'Dancing....'
            }
        }
    }
}
