#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('deploy') {
            environment {
              AWS_ACCESS_KEY_ID = credentials('aws_access_key_id')
              AWS_SECRET_ACCESS_KEY = credentials('aws_secret_key')
            }
            steps {
                script {
                    echo 'deploying kubernetes pods...'
                    sh 'whoami'
                    sh 'kubectl get nodes'
                    sh 'kubectl create deployment nginx-deployment --image=nginx'
                    }
                }
            }
        }
    }
