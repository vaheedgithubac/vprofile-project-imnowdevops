pipeline {
    agent { label 'maven'}
    tools {
        maven 'maven-396'
        }
        
    stages {
        stage('Copy docker-compose.yml') {
            steps {
                    sshagent(['jenkins-agent']) {
                     sh """
                         scp -o StrictHostKeyChecking=no docker-compose.yml jenkins-agent@172.31.24.126:/home/jenkins-agent/
                         ssh jenkins-agent@172.31.24.126:/home/jenkins-agent/docker-compose up -d
                        """
            }
           }
        }
    }
}
