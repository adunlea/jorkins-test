pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/adunlea/jorkins-test.git'
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
            steps {
                when {
                    expression { return env.BRANCHNAME == 'production'}
                }
                steps {
                    echo 'Deploying for production...'
                } 
            }
        }
        stage('Dance Party') {
            steps {
                echo 'Dancing....'
            }
        }
    }
}
