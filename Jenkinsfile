pipeline {
    agent any
    
    options {
        skipDefaultCheckout true
    }
    
    stages {
        stage('Build Backend') {
            when {
                branch 'production'
            }
            steps {
                dir('Bellerophon') {
                    git branch: 'production', url: 'https://github.com/adunlea/Bellerophon.git'
                }
            }
        }
        stage('Build') {
            steps {
                
                echo 'Building..'
                echo "branch: ${env.BRANCH_NAME}"
                
                dir('Jorkins') {
                    checkout scm   
                }
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
