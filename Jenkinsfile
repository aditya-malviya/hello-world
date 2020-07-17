pipeline {
    agent any 
    stages {
        stage('Build') {
            parallel {
                stage('Maven build') {
                    steps {
                        sh "mvn clean package"    
                    }
                }
                stage('Checkstyle') {
                    steps {
                        sh "mvn checkstyle:check"
                        recordIssues(tools: [checkStyle(reportEncoding: 'UTF-8')])
                    }
                }
            }
        }
    }
}
