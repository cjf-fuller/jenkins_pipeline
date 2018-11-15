pipeline {
    agent any
    ironment {
        providerId = "NULL"
    }
    stages {
        stage('identifyProvider') {
            steps {
                sh '''#!/bin/bash
            ${providerId} = ($(curl https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json | jq '.providerId'))
            echo ${providerId} 
        '''
            }
        }
        stage('selectProvider') {
            steps {
                script {
                     if (providerId == 'azr')
            {
                echo providerId
            }
            else if (providerId == 'aws')
            {
                echo providerId
            }
            else if (providerId == 'gcp')
            {
                echo providerId
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