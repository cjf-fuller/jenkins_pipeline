pipeline {
    agent any
    parameters {
        choice(choices: 'yes\nno', description: 'Is deployment Azure?', name: 'azr')
        choice(choices: 'yes\nno', description: 'Is deployment AWS?', name: 'aws')
        string(defaultValue: "caspar.fuller95@gmail.com", description: 'email for notifications', name: 'notification_email')
    }
    stages {
        stage('azure') {
            when {
                environment name: 'azr', value: 'yes'
            }
            steps {
                echo "Azure"
            }
        }
        stage('aws/gcp parallel') {
            steps {
                script{
                        if (env.aws == 'yes')
                        {
                                echo "Aws"
                        }
                        else 
                        {
                                 echo "Gcp"
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