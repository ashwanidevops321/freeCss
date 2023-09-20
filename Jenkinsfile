pipeline {
    agent any
    environment {
        staging_server = "20.150.193.70"
    }

    stages {
        stage("Deploy to Remote") {
            steps {
                script {
                    // Use the correct path to the jenkins-pipeline directory without the trailing slash
                    sh "scp -r -i /var/lib/jenkins/.ssh/id_rsa ${WORKSPACE}/jenkins-pipeline jenkins@${staging_server}:/var/www/html/"
                }
            }
        }
    }
}
