pipeline {
    agent any  // Remplacer 'linux' par 'any' si tu veux utiliser n'importe quel agent disponible

    options {
        buildDiscarder logRotator(
            numToKeepStr: '5'
        )
    }

    stages {
        stage('Scan') {
            steps {
                withSonarQubeEnv(installationName: 'sql') {  // Correction du nom de la fonction
                    sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'  // Espaces après sh pour une meilleure lisibilité
                }
            }
        }
    }
}


