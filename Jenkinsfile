pipeline {
    agent any
    //triggers { pollSCM('* * * * *') }
    environment {
        HUGO_PUBLIC_PATH     = credentials('hugo-path')
        INTRA_IP = credentials('hugo-ip')
        HUGO_DOMAIN = credentials('hugo-domain')

    }
    stages {
        stage('clean') {
            steps {
                sh 'rm -rf $HUGO_PUBLIC_PATH{*,.*}'
            }
        }
        stage('Build') {
            steps {
                dir('home'){
                    sh '/home/linuxbrew/.linuxbrew/bin/hugo -d $HUGO_PUBLIC_PATH --baseURL $HUGO_DOMAIN --noTimes'
                }
            }
        }
    }
}