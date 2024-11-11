pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Clonez le code source depuis un dépôt Git
                checkout scm
            }
        }
        stage('Compile') {
            steps {
                // Compile le fichier Java
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                // Exécute le programme Java
                sh 'java HelloWorld'
            }
        }
    }
}