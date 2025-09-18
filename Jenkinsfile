pipeline {
    agent any

    environment {
        USERNAME = "esha"
        SERVER = "192.168.149.133"   // yahan apne Ubuntu Jenkins server ka IP
        DEPLOY_PATH = "/var/www/test"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:EshaAshfaq-ITstudent/welcomeDevops.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh """
                    sudo cp ${WORKSPACE}/welcome.html ${DEPLOY_PATH}/
                    sudo systemctl restart apache2
                """
            }
        }
    }
}
