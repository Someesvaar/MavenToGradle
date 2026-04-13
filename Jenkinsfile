pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'
        gradle 'Gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Someesvaar/MavenToGradle.git'
            }
        }

        stage('Build Maven') {
            steps {
                sh 'mvn clean install'  // Run Gradle build
            }
        }

        stage('Migrate Maven to Gradle') {
            steps {
                sh 'gradle init --type pom'  // Run Gradle build
            }
        }


        
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
