pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Clone the repository
                git branch: 'master', url: 'https://github.com/your-repo.git'
                
                // Build the application on the remote server
                sshagent(['your-remote-ssh-credentials']) {
                    sh 'ssh your-remote-user@your-remote-server "cd /path/to/your/application && mvn clean package"'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application on the remote server
                sshagent(['your-remote-ssh-credentials']) {
                    sh 'ssh your-remote-user@your-remote-server "cd /path/to/your/application && ./deploy.sh"'
                }
            }
        }
    }
}

