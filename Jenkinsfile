pipeline {
    agent none

    stages {
        stage('SSH and deploy') {
            steps {
                script {
                    // Replace with actual credentials from Jenkins Credentials Management
                    def username = credentialsId('your_ssh_username_credential_id', type: 'usernamePassword')
                    def password = credentialsId('your_ssh_password_credential_id', type: 'usernamePassword')
                    def server_ip = server_ip_1.146
                    // Use SSH Agent plugin for secure authentication
                    sshAgent(credentials: [privateKey]) {
                        ssh(
                            credentials: username,
                            host: server,
                            command: 'docker-compose up -d' // Run docker-compose in detached mode
                        )
                    }
                }
            }
        }
    }
}

