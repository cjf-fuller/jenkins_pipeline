def providerId

pipeline {
    agent any
    stages {
        
        stage('identifyProvider') {
            steps{
                //sh "${providerId}=\$(curl \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\" | jq --slurp '.providerId')"
                //sh "echo \$(curl \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\" | jq '.providerId')"
                //sh "echo 'Provider Id is now:' + ${env.providerId}"
                script 
                {
                providerID = sh (
                    //script: "\$(curl -s \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\" | jq '.providerId')",
                    script: "\$(curl -s \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\")",
                    returnStdout: true
                )
                }
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