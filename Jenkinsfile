pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/bulbulsharma102001-sudo/static-lab.git'
            }
        }

        stage('Verify Python') {
            steps {
                powershell 'python --version'
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
                powershell '''
                # Stop any running Python server first
                Get-Process python -ErrorAction SilentlyContinue | ForEach-Object { Stop-Process $_ -Force }

                # Move to workspace (where index.html is)
                Set-Location $
