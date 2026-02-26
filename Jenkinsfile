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

                sudo rm -rf /var/www/html/*
                sudo cp -r * /var/www/html/
                '''
            }
        }

        stage('Restart Web Server') {
            steps {
                sh '''
                sudo systemctl restart apache2 || sudo systemctl restart nginx
                '''
            }
        }
    }

}
