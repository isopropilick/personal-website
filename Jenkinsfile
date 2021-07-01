pipeline {
    agent any
    environment {
        HUGO_PUBLIC_PATH     = credentials('hugo-path')
        INTRA_IP = credentials('hugo-ip')
        HUGO_DOMAIN = credentials('hugo-domain')

    }
    stages {
        stage('clean') {
            steps {
                sh 'rm -rfv $HUGO_PUBLIC_PATH/*'
            }
        }
        stage('Build') {
            steps {
                sh 'cd home/'
                sh 'ls'
                sh '/home/linuxbrew/.linuxbrew/bin/hugo -d $HUGO_PUBLIC_PATH --baseURL $HUGO_DOMAIN'
            }
        }
    }
}