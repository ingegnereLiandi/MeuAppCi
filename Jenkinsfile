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
                bat "node -v"
                bat 'npm install'
                bat 'npm run build'
            }
        }
        stage('Run Unit Tests') {
            steps{
                bat 'npm run test' 
                }
            }
        }
    }
