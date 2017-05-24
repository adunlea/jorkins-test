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
                if($env.BRANCH_NAME == 'production') {
                    echo 'Deploying for production...'
                } else {
                    echo "Deploying for something else...'
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
