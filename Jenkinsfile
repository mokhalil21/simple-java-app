node {
    try {
        stage('Checkout') {
            git branch: 'main', url: 'https://github.com/mokhalil21/simple-java-app.git'
        }

        stage('build') {
            sh 'echo "build stage"'
        }

        stage('test') {
            if (env.BRANCH_NAME == 'feat') {
                sh 'echo "test stage"'
            } else {
                sh 'echo "skip test stage"'
            }
        }
    } catch (Exception e) {
        sh 'echo "exception found"'
        throw e
    }
}
