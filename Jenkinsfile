pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            steps {
                // Utiliser le chemin complet de javac pour compiler le fichier Java
                bat '"C:\\Program Files\\Java\\jdk-21\\bin\\javac" HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                // Utiliser le chemin complet de java pour exécuter le programme
                bat '"C:\\Program Files\\Java\\jdk-21\\bin\\java" HelloWorld'
            }
        }

        stage('SonarQube Analysis') {
    steps {
        script {
            // Exécuter l'analyse SonarQube
            def scannerHome = tool 'SonarQubeScanner'  // Assurez-vous que 'SonarQubeScanner' est configuré
            withSonarQubeEnv('SonarQube') { // Assurez-vous que 'SonarQube' est bien défini dans Jenkins
                bat "${scannerHome}\\bin\\sonar-scanner.bat"
            }
        }
    }
}



    }
}
