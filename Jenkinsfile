pipeline {
    agent any 
    stages {
        stage('Build') {
            parallel {
                stage('Maven build') {
                    steps {
                        sh "sudo mvn clean package"    
                    }
                }
                stage('Checkstyle') {
                    steps {
                        sh "sudo mvn checkstyle:check"
                        recordIssues(tools: [checkStyle(reportEncoding: 'UTF-8')])
                    }
                }
            }
        }
    }
}
