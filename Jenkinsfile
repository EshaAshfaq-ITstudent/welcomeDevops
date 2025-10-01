pipeline {
    agent any

    environment {
        USERNAME = "esha"
        SERVER = "192.168.149.133"
        DEPLOY_PATH = "/var/www/test"
    }

    stages {
        stage('Deploy to Apache') {
            steps {
                sh """
                    rsync -av --delete --exclude ".git/" --exclude "Jenkinsfile" ${WORKSPACE}/ ${USERNAME}@${SERVER}:${DEPLOY_PATH}/
                    ssh ${USERNAME}@${SERVER} "sudo systemctl restart apache2"
                """
            }
        }
    }
}
