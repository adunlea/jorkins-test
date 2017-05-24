pipeline {
    agent any
    
    options {
        skipDefaultCheckout true
    }
    
    stages {
        stage('Build Backend') {
            when {
                branch 'production*'
            }
            steps {
                dir('Bellerophon') {
                    git branch: "${env.BRANCH_NAME}", url: 'https://github.com/adunlea/Bellerophon.git'
                    stash 'REALLYIMPORTANT.txt'
                }
            }
        }
        stage('Build') {
            steps {
                
                echo 'Building..'
                echo "branch: ${env.BRANCH_NAME}"
                
                dir('Jorkins') {
                    checkout scm
                    unstash 'REALLYIMPORTANT.txt'
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
