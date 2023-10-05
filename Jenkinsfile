pipeline{
    agent any
    tools{
        nodejs "node 16.17.0"
    }

    stages{
        stage('Checkout') {
            steps{
                checkout([$class:'GitSCM', branches:[[name:'*/main']], userRemoteConfigs:[[url:'https://github.com/ingegnereLiandi/MeuAppCi.git']]])
            }
        }

        stage('Build') {
            steps{
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Run Unit Tests') {
            steps{
                sh 'npm run test'
                }
            }
        }
    }
