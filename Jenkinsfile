pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        }
    }
}
