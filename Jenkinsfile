pipeline {
    agent any
    parameters {
        providerId = 'NULL'
    }
    stages {
        stage('identifyProvider') {
            bash '''#!/bin/bash
            ${env.providerId}=($(curl https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json | jq '.providerId'))
            echo ${env.providerId} 
        '''
        
        }
        stage('selectProvider') {
            if (env.providerId == 'azr')
            {
                echo 'azr'
            }
            else if (env.providerId == 'aws')
            {
                echo 'aws'
            }
            else if (env.providerId == 'gcp')
            {
                echo 'gcp'
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