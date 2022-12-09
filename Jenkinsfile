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
               docker build . -t "${JOB_BASE_NAME}-${BUILD_NUMBER}"
               
            }
                }
    }
}
