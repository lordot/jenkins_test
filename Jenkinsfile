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
                    withKubeConfig([credentialsId: 'lke-configdfile', serverUrl: 'https://06689cbd-962c-42c5-bb54-8bef03b752ae.eu-central-1.linodelke.net']) {
                        sh 'whoami'
                        sh 'kubectl get nodes'
                        sh 'kubectl create deployment nginx-deployment --image=nginx'
                        }
                    }
                }
            }
        }
    }
