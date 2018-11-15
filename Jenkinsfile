def providerId
def rootschema

pipeline {
    agent any
    stages {
        
        stage('identifyProvider') {
            steps{
                script 
                {
                providerId = sh (
                    script: "echo \$(curl -s \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\" | jq '.providerId')",
                    returnStdout: true
                ).trim()
                rootschema = sh (
                    script: "echo \$(curl -s \"https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json\")",
                    returnStdout: true
                ).trim()
                }
            }  
        }
        stage('selectProvider') {
            steps {
                script {
                     if (providerId == 'azr')
            {
                echo 'azr'
            }
            else if (providerId == 'aws')
            {
                echo 'aws'
            }
            else if (providerId == 'gcp')
            {
                echo 'gcp'
            }
            else
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