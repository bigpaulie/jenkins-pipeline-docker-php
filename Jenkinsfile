pipeline {
    agent none
    stages {
        stage('PHP CLI') {
            agent {
                docker { image 'php:7.2-cli' }
            }
            steps {
              sh 'php -f index.php > phpinfo.html'
            }
            post {
                always {
                    archiveArtifacts artifacts: '*.html', fingerprint: true
                }
            }
        }
    }
}
