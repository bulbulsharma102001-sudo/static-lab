pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/bulbulsharma102001-sudo/static-website.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Static website — build not required.'
            }
        }

        stage('Run Website') {
            steps {
                echo 'Starting local web server on port 8085...'
                
                // Run Python HTTP server in background using PowerShell
                powershell """
                Start-Process powershell -ArgumentList '-NoExit', '-Command', 'python -m http.server 8085' -WindowStyle Hidden
                """
                
                echo 'Server started! Access at http://localhost:8085'
            }
        }
    }
}
