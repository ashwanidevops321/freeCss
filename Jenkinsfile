pipeline {
    agent any
    environment {
        staging_server = "20.163.29.223"
    }
    stages {
        stage("Deploy to Remote") {
            steps {
                script {
                    // Use scp to copy files to the remote host
                    sh """
                    scp -r /var/lib/jenkins/workspace/pipeline-project/* root@${staging_server}:/var/www/
                    """
                }
            }
        }
    }
}
