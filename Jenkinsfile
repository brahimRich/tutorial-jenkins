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
                    // Assurez-vous que 'SonarQubeScanner' est configuré correctement dans Jenkins
                    def scannerHome = tool 'SonarQubeScanner'  
                    withSonarQubeEnv('SonarQube') { 
                        bat "${scannerHome}\\bin\\sonar-scanner.bat"
                    }
                }
            }
        }
    }
}
