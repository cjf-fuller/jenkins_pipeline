pipeline {
    agent any
    environment {
        providerId = "NULL"
    }
    stages {
        stage('identifyProvider') {
            steps {
                //sh "${providerId}=\$(curl \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\" | jq --slurp '.providerId')"
                sh "${providerId}=\$(curl \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\")"
                sh "echo 'Provider Id is now:' + ${providerId}"
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