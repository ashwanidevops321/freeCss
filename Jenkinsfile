pipeline {
    agent any
    environment {
        staging_server = "20.150.193.70"
    }

    stages {
        stage("Deploy to Remote") {
            steps {
                script {
                    sh "scp -r ${WORKSPACE}/* azureuser@${staging_server}:/var/www/html/"
                }
            }
        }
    }
}
