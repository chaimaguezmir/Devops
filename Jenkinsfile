pipeline {
    agent any
    environment {
        MAVEN_HOME = "/opt/apache-maven-3.6.3"
        PATH = "$MAVEN_HOME/bin:$PATH"
    }
    stages {
        stage('Scan') {
            steps {
                withSonarQubeEnv('sq1') {
                    sh '$MAVEN_HOME/bin/mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                }
            }
        }
    }
}


