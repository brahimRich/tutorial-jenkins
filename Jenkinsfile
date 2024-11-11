pipeline {
    agent any

    tools {
        // Utilisez SonarRunnerInstallation comme outil au lieu de sonarQubeScanner
        sonarQube 'SonarQubeScanner'  // Assurez-vous que 'SonarQubeScanner' est le nom configuré dans Jenkins
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
