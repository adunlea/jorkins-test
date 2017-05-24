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
        
        
        
        if(env.BRANCH_NAME == 'production')
        {
            stage('Deploy') {
                steps {
                    echo 'Deploying....'
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
