pipeline {
    agent any
    environment {
        providerId = "NULL"
    }
    stages {
        stage('identifyProvider') {
            steps {
                script{
                    env.providerId = sh(
                        script: '''curl https://raw.githubusercontent.com/cjf-fuller/jenkins_pipeline/master/AwsSampleJsonPayload.json | jq -r '. | .providerId' ''',
                        returnStdout: true).trim()
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