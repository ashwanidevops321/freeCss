pipeline {
    agent any
    environment{
        staging_server="20.150.193.70"
    }

    stages{
        stage("Deploy to Remote"){
            steps{
                sh "sh 'scp ${WORKSPACE}/* jenkins@${staging_server}:/var/www/html'"
            }
            }
        }
    }
