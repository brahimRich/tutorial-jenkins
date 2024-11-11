pipeline {
    agent any

    tools {
        sonarQubeScanner 'SonarQubeScanner' // Assurez-vous que le nom correspond à celui que vous avez configuré
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            steps {
                bat '"C:\\Program Files\\Java\\jdk-21\\bin\\javac" HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                bat '"C:\\Program Files\\Java\\jdk-21\\bin\\java" HelloWorld'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                script {
                    // Exécuter l'analyse SonarQube
                    sh 'sonar-scanner'
                }
            }
        }
    }
}
