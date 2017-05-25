pipeline {
    agent any
    
    options {
        skipDefaultCheckout true
    }
    
    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()   
            }
        }
        stage('Build Backend') {
            when {
                branch 'production*'
            }
            steps {
                checkout([$class: 'GitSCM', branches: [[name: "*/${env.BRANCH_NAME}"]], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'Bellerophon-GOOSE']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a3a4c2c2-d68d-4a7c-a2d3-d3cb3d297ce8', url: 'https://github.com/adunlea/Bellerophon.git']]])
                dir('Bellerophon-GOOSE') {
                    stash 'REALLYIMPORTANT.txt'
                }
            }
        }
        stage('Build') {
            steps {
                
                echo 'Building..'
                echo "branch: ${env.BRANCH_NAME}"
                
                dir('Johorokins') {
                    checkout scm
                    dir('testfolder') {
                        unstash 'REALLYIMPORTANT.txt'
                    }
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
