pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Voer hier commando's uit om de toepassing naar de server te kopiëren en opnieuw te starten
                    // Bijvoorbeeld: scp, ssh, systemctl restart, enz.
                    sh 'scp -r ./dist user@your-server:/path/to/destination'
                    sh 'ssh user@your-server "cd /path/to/destination && npm install && npm start"'
                }
            }
        }
    }
}

