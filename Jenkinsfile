pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out to main branch'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git']])
                withPythonEnv('python') {
                    sh 'make install'
                    sh 'make test'
                }
            }
        }
    }
}
