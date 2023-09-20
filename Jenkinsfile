pipeline {
    agent any
    environment {
        staging_server = "20.163.29.223"
        ssh_key = credentials('121') // Replace with your SSH credentials ID
    }
    stages {
        stage("Deploy to Remote") {
            steps {
                script {
                    // Use sshagent to handle SSH key and host key verification
                    sshagent(credentials: [ssh_key]) {
                        sh """
                        scp -i ${ssh_key} -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/* azureuser@${staging_server}:/var/www/
                        """
                    }
                }
            }
        }
    }
}
