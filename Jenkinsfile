pipeline {
    agent any
    stages {
        stage('Deploy app (mock)') {
            steps {
                sh "echo 'building SUT....'"
                sh "sleep 10"
                sh "echo 'deploying SUT....'"
                sh "sleep 10"
            }
        }

        stage('Testing') {
                    steps {
                        sh "mvn clean verify"
                        publishHTML (target: [
                                             allowMissing: false,
                                             alwaysLinkToLastBuild: false,
                                             keepAll: true,
                                             reportDir: 'target/site/serenity',
                                             reportFiles: 'index.html',
                                             reportName: "RCov Report"
                                         ])
                    }
                }

    }

}
