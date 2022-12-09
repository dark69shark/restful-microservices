pipeline {
    agent {
        label 'jenkins-dind'
    }

    stages {
        stage('Static Test, lint sooon') {
            steps {
                sh 'ls -la'
            }
        }
                stage('Buiild') {
            steps {
                sh "docker build . -t ${JOB_BASE_NAME}:${BUILD_NUMBER}"
            }}
            stage('Test run') {
            steps {
                sh "docker run --rm -p8080:8080 ${JOB_BASE_NAME}:${BUILD_NUMBER}"
                sh 'curl http://127.0.0.1:8080'
            }
            }

        stage('Push') {
            steps {
                sh "docker tag ${JOB_BASE_NAME}:${BUILD_NUMBER} 192.168.200.1:8081/artifcatory/docker/${JOB_BASE_NAME}:${BUILD_NUMBER}"
                sh "docker push 192.168.200.1:8081/artifcatory/docker/${JOB_BASE_NAME}:${BUILD_NUMBER}"
            }
        }
                }
    }
