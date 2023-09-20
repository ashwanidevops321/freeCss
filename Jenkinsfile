pipeline {
    agent any
    environment{
        staging_server="20.163.29.223"
    }

    stages{
        stage("Deploy to Remote"){
            steps{
                sh "sh 'scp ${WORKSPACE}/* azureuser@${staging_server}:/var/www/'"
            }
            }
        }
    }
