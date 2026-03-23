pipeline {
    agent any

    tools {
        maven 'Maven'   // Must match the name configured in Jenkins → Global Tool Configuration
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        }
    }
}
