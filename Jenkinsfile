pipeline {
    agent any

    stages {
        stage('Deploy to Remote') {
            steps {
                script {
                    // Use scp to copy files to the remote host
                    sh """
                    scp /var/lib/jenkins/workspace/pipeline-project/* my-remote-host:/var/www/html/
                    """
                }
            }
        }
    }
}
