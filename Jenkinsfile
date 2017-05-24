pipeline {
    agent none

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/adunlea/jorkins-test.git'
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
