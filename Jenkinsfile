pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                cp /var/www/html/index.html /var/www/html/index.html1
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
