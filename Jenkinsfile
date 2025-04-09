pipeline {
    agent any

    stages {
        stage('Buil') {
            agent {
                docker {
                    image 'node:20-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo 'Jenkins va installer les deps du projet'
                ls -al 
                npm ci
                echo 'Jenkins va créer le build'
                npm run build
                echo 'fin'
                ls -al
                '''
            }
        }
    }
}
