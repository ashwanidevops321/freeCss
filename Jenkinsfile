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
                        scp -o StrictHostKeyChecking=no -i \$SSH_KEY \
                            /var/lib/jenkins/workspace/pipeline-project/Jenkinsfile \
                            /var/lib/jenkins/workspace/pipeline-project/about.html \
                            /var/lib/jenkins/workspace/pipeline-project/ashwani.txt \
                            /var/lib/jenkins/workspace/pipeline-project/contact.html \
                            /var/lib/jenkins/workspace/pipeline-project/css/file.css \
                            /var/lib/jenkins/workspace/pipeline-project/fileA \
                            /var/lib/jenkins/workspace/pipeline-project/fonts/font.ttf \
                            /var/lib/jenkins/workspace/pipeline-project/games.html \
                            /var/lib/jenkins/workspace/pipeline-project/images/image.png \
                            /var/lib/jenkins/workspace/pipeline-project/index.html \
                            /var/lib/jenkins/workspace/pipeline-project/js/script.js \
                            /var/lib/jenkins/workspace/pipeline-project/tranner.html \
                            azureuser@${staging_server}:/var/www/html/
                        """
                    }
                }
            }
        }
    }
}
