pipeline {
    agent any

    stages {
        stage('Build Backend') {
            when {
                branch 'production'
            }
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/production']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/adunlea/Bellerophon.git']]])   
            }
        }
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
