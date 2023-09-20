pipeline {
    agent any
    environment {
        staging_server = "20.150.193.70"
    }

    stages {
        stage("Deploy to Remote") {
            steps {
                script {
                    // Use WORKSPACE variable to reference Jenkins workspace
                    sh "scp -r ${WORKSPACE}/jenkins-pipeline/* jenkins@${staging_server}:/var/www/html/"
                }
            }
        }
    }
}
