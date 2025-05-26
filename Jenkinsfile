pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aksyntax/devopspipe1.git'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Publishing HTML report...'
                publishHTML(target: [
                    reportDir: '.',                 // Directory with index.html
                    reportFiles: 'index.html',      // File to publish
                    reportName: 'Build Report',     // Display name in Jenkins
                    allowMissing: false,
                    alwaysLinkToLastBuild: true,
                    keepAll: true
                ])
            }
        }
    }
}
