pipeline {
    agent { label "balaji"}

    triggers {
        pollSCM('* * * * *')
    }
    
    stages {
        stage('stagee1') {
            steps {
                echo 'clone the project'
                git branch: 'main', url: 'https://github.com/RBalaji123/htmlproject-balaji.git'
            }
        }
              stage('stage2') {
            steps {
                echo 'verify the file where it is cloned'
                sh '''pwd'''
                sh '''ls'''
            }
        }
              stage('stage3') {
            steps {
                echo 'copy the file'
                sh 'scp -i /home/ec2-user/devops.pem -r /var/jenkins/workspace/devops_project/* ec2-user@3.27.168.116:/var/www/html'
            }
        }
              stage('stage4') {
            steps {
                echo 'Deploy'
            }
        }
    }
}
