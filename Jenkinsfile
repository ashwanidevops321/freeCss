pipeline {
    agent any

    stages {
        stage('Deploy to Remote') {
            steps {
                script {
                    // Use scp to copy files to the remote host
                    sh """
                    scp /var/lib/jenkins/workspace/pipeline-project/* azureuser@20.163.29.223:/var/www/html
                    """
                }
            }
        }
    }
}
