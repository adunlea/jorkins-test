pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
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
                echo "It's production party time!"
            }
        }
        stage('Dance Party') {
            steps {
                echo 'Dancing....'
            }
        }
    }
}
