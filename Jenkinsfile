pipeline {
    agent any
    environment {
        HUGO_PUBLIC_PATH     = credentials('hugo-path')
        INTRA_IP = credentials('hugo-ip')
        HUGO_DOMAIN = credentials('hugo-domain')

    }
    stages {
        stage('Build') {
            steps {
                sh("hugo -d $HUGO_PUBLIC_PATH --bind $INTRA_IP --baseURL $HUGO_DOMAIN -t own")
            }
        }
    }
}