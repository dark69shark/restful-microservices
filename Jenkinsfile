pipeline {
    agent {
        label 'jenkins-dind'
    }

    stages {
        stage('Example Test') {
            steps {
                sh 'ls -la'
            }
        }
                stage('Buiild') {
            steps {
               sh "docker build . -t ${JOB_BASE_NAME}-${BUILD_NUMBER}"
               
            }
                }
    }
}