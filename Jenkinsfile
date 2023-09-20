pipeline {
    agent any
    environment {
        staging_server = "20.150.193.70"
    }

    stages {
        stage("Accept Host Key") {
            steps {
                script {
                    // Use SSH command to connect and accept the host key
                    sh "ssh -o StrictHostKeyChecking=no ${staging_server}"
                }
            }
        }

        stage("Deploy to Remote") {
            steps {
                script {
                    // Perform the SCP transfer after host key has been accepted
                    sh "scp -r ${WORKSPACE}/* azureuser@${staging_server}:/var/www/html/"
                }
            }
        }
    }
}
