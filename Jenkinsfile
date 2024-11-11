pipeline {
    agent any

    tools {
        sonar 'SonarQubeScanner'  // Nom configuré dans Jenkins pour l'outil SonarQube
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
                    bat 'sonar-scanner'
                }
            }
        }
    }
}
