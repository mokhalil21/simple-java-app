pipeline {
    agent { label 'ec2-agent' }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mokhalil21/simple-java-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package' // Corrected the command here
            }
        }

        stage('Test') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'feat') {
                        sh 'echo "test stage"'
                    } else {
                        sh 'echo "skip test stage"'
                    }
                }
            }
        }
    }

    post {
       sucess {
           slackSend channel: '#jenkins-ci', message: "Build sucess - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'project-5rk8017', tokenCredentialId: 'slack-notification'
        }
        
  failure {
   slackSend channel: '#jenkins-ci', message: "Build failed - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'project-5rk8017', tokenCredentialId: 'slack-notification'
  }

    }
    
}
