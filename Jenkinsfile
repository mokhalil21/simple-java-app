pipeline {
    agent { label 'ec2-agent' }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', ursfl: 'https://github.com/mokhalil21/simple-java-app.git'
            }fdsf
        }

        stage('Build') {fsd
            steps {
                sh 'mvn clean package' // Corrected the command here
            }
        }dfsfsf
dsf
                }
            }
        }
    }

    post {
        success { // Corrected the spelling hsdfere
            slackSend(channel: '#jenkins-ci', message: "Build success - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'project-5rk8017', tokenCredentialId: 'slack-notification')
        }
        
        failure {
            slackSend(channel: '#jenkins-ci', message: "Build failed - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'project-5rk8017', tokenCredentialId: 'slack-notification')
        }
    }   
}
