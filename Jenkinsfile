pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                script {
                    echo "build in progress"
                }
            }
node {
    git branch: 'main', url: 'https://github.com/mokhalil21/simple-java-app.git'

    stage('build') {
        try {
            sh 'echo "build stage"'
        } catch (Exception e) {
            sh 'echo "exception found"'
            throw e
        }
        stage('test') {
            steps {
                script {
                    echo "test in progress"
                }
            }
    }

    stage('test') {
        if (env.BRANCH_NAME == 'feat') {
            sh 'echo "test stage"'
        } else {
            sh 'echo "skip test stage"'
        }
    }
}
