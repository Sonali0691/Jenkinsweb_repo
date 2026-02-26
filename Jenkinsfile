pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Sonali0691/Jenkinsweb_repo.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Deploying application..."

                rm -rf /var/www/html/*
                cp -r * /var/www/html/
                '''
            }
        }

        stage('Restart Web Server') {
            steps {
                sh '''
                systemctl restart apache2 || systemctl restart nginx
                '''
            }
        }
    }

}
