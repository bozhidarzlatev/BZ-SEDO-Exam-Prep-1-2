pipeline {
    agent {
        label any
    }


    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }


        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution complete.'
        }
    }
}
