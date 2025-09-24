pipeline {
    agent any

    environment {
        USERNAME = "esha"
        SERVER = "192.168.149.133"   // yahan apne Ubuntu Jenkins server ka IP
        DEPLOY_PATH = "/var/www/myweb"
    }

    stages {
       
        stage('Deploy to Apache') {
            steps {
                sh """
                    rsync -av --exclude ".git/" --exclude "Jenkinsfile" ${WORKSPACE}/* ${USERNAME}@${SERVER}:${DEPLOY_PATH}/
                    sudo systemctl restart apache2
                """
            }
        }
    }
}
