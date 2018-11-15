pipeline {
    agent any
    parameters {
        string(name: 'providerId', defaultValue: 'NULL')
    }
    stages {
        stage('identifyProvider') {
            steps {
                sh '''#!/bin/bash
            ${params.providerId} = ($(curl https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json | jq '.providerId'))
            echo ${params.providerId} 
        '''
            }
        }
        stage('selectProvider') {
            steps {
                script {
                     if (params.providerId == 'azr')
            {
                echo 'azr'
            }
            else if (params.providerId == 'aws')
            {
                echo 'aws'
            }
            else if (params.providerId == 'gcp')
            {
                echo 'gcp'
            }
                }
            }
        }
    }
post {
        success {
            echo "Test succeeded"
        }
        failure {
            echo "Test failed"
        }
    }
}