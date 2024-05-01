pipeline {
    agent { label 'maven'}
    tools {
        maven 'maven-396'
        }
        
    stages {
        stage('Copy docker-compose') {
            sshagent(['jenkins-agent']) {
                sh """
                      scp -o StrictHostKeyChecking=no docker-compose.yml jenkins-agent@172.31.24.126:/home/jenkins-agent/
                      
                      //ssh jenkins-agent@172.31.24.126:/home/jenkins-agent/docker-compose up -d
                    
                      //ssh ec2-user@172.31.42.229 /opt/tomcat-85/bin/startup.sh

                 """
           }
        }
    }
}
